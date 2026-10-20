---
title: "Log di ricerca - Manuale del commerciante e Guida alla configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Log di ricerca di MyPresta.eu."
sidebar:
  label: "Log di ricerca - Manuale del commerciante e Guida alla configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Search log su MyPresta.eu](https://mypresta.eu/modules/administration-tools/search-log.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/back-office-tools/search-log/)
>
> ---


# Log di ricerca

## 1. Requisiti e compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono generalmente sufficienti. Nessun requisito speciale oltre a un ambiente di hosting PrestaShop standard.

## 2. Panoramica completa della configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura > Log di ricerca)

Questa è la schermata di configurazione principale per il modulo "Log di ricerca". Fornisce un'interfaccia semplice per abilitare o disabilitare la funzionalità di logging.

-   **Posizione del menu:** Back Office > Moduli > Gestione moduli > Log di ricerca > Configura

| Impostazione / Opzione | Cosa fa questa impostazione | Effetto della modifica di questa impostazione | Valore consigliato | Scenario / esempio del commerciante |
| :--- | :--- | :---
```json
{
  "name": "Search log",
  "description": "Records customer search queries on your PrestaShop store.",
  "version": "1.0.0",
  "author": "MyPresta.eu",
  "tab": "administration",
  "is_configurable": 1,
  "ps_versions_compliancy": {
    "min": "1.6.0.0",
    "max": "9.0.0.0"
  },
  "php_versions_compliancy": {
    "min": "5.6",
    "max": "8.5"
  }
}
```

## 3. 8 Module Class (`searchlog.php`)

This is the main module class file, `searchlog.php`. It contains the core logic for installation, uninstallation, configuration, and hook implementations.

```php
<?php
/**
 * 2007-2024 PrestaShop
 *
 * NOTICE OF LICENSE
 *
 * This source file is subject to the Academic Free License (AFL 3.0)
 * that is bundled with this package in the file LICENSE.txt.
 * It is also available through the world-wide-web at this URL:
 * http://opensource.org/licenses/afl-3.0.php
 * If you did not receive a copy of the license and are unable to
 * obtain it through the world-wide-web, please send an email
 * to license@prestashop.com so we can send you a copy immediately.
 *
 * DISCLAIMER
 *
 * Do not edit or add to this file if you wish to upgrade PrestaShop to newer
 * versions in the future. If you wish to customize PrestaShop for your
 * needs please refer to http://www.prestashop.com for more information.
 *
 * @author    PrestaShop SA <contact@prestashop.com>
 * @copyright 2007-2024 PrestaShop SA
 * @license   http://opensource.org/licenses/afl-3.0.php  Academic Free License (AFL 3.0)
 * International Registered Trademark & Property of PrestaShop SA
 */

if (!defined('_PS_VERSION_')) {
    exit;
}

class Searchlog extends Module
{
    protected $config_form = false;

    public function __construct()
    {
        $this->name = 'searchlog';
        $this->tab = 'administration';
        $this->version = '1.0.0';
        $this->author = 'MyPresta.eu';
        $this->need_instance = 0;

        /**
         * Set $this->bootstrap to true if your module is compliant with bootstrap (PrestaShop 1.6)
         */
        $this->bootstrap = true;

        parent::__construct();

        $this->displayName = $this->l('Search log');
        $this->description = $this->l('Records customer search queries on your PrestaShop store.');

        $this->ps_versions_compliancy = array('min' => '1.6', 'max' => _PS_VERSION_);
    }

    /**
     * Don't forget to create update methods if needed:
     * http://doc.prestashop.com/display/PS16/Enabling+the+Auto-Update
     */
    public function install()
    {
        if (parent::install() &&
            $this->registerHook('displayHeader') &&
            $this->registerHook('displayBackOfficeHeader') &&
            $this->registerHook('actionSearch') &&
            $this->registerHook('actionModuleInstall') &&
            $this->registerHook('actionModuleUninstall') &&
            $this->installTab() &&
            $this->createSlogTable()
        ) {
            Configuration::updateValue('SEARCHLOG_LIVE_MODE', false);
            return true;
        }
        return false;
    }

    public function uninstall()
    {
        if (!parent::uninstall() ||
            !Configuration::deleteByName('SEARCHLOG_LIVE_MODE') ||
            !$this->uninstallTab() ||
            !$this->dropSlogTable()
        ) {
            return false;
        }
        return true;
    }

    /**
     * Load the configuration form
     */
    public function getContent()
    {
        /**
         * If values have been submitted in the form, process them.
         */
        if (((bool)Tools::isSubmit('submitSearchlogModule')) == true) {
            $this->postProcess();
        }

        $this->context->smarty->assign('module_dir', $this->_path);

        $output = $this->context->smarty->fetch($this->local_path . 'views/templates/admin/configure.tpl');

        return $output . $this->renderForm();
    }

    /**
     * Create the form that will be displayed in the configuration of your module.
     */
    protected function renderForm()
    {
        $helper = new HelperForm();

        $helper->show_toolbar = false;
        $helper->table = $this->table;
        $helper->module = $this;
        $helper->default_form_language = $this->context->language->id;
        $helper->allow_employee_form_lang = Configuration::get('PS_BO_ALLOW_EMPLOYEE_FORM_LANG', 0);

        $helper->identifier = $this->identifier;
        $helper->submit_action = 'submitSearchlogModule';
        $helper->currentIndex = $this->context->link->getAdminLink('AdminModules', false)
            . '&configure=' . $this->name . '&tab_module=' . $this->tab . '&module_name=' . $this->name;
        $helper->token = Tools::getAdminTokenLite('AdminModules');

        $helper->tpl_vars = array(
            'fields_value' => $this->getConfigFormValues(), /* Add values for your inputs */
            'languages' => $this->context->controller->getLanguages(),
            'id_language' => $this->context->language->id,
        );

        return $helper->generateForm(array($this->getConfigForm()));
    }

    /**
     * Create the structure of your form.
     */
    protected function getConfigForm()
    {
        return array(
            'form' => array(
                'legend' => array(
                    'title' => $this->l('Settings'),
                    'icon' => 'icon-cogs',
                ),
                'input' => array(
                    array(
                        'type' => 'switch',
                        'label' => $this->l('Enable Search Log'),
                        'name' => 'SEARCHLOG_LIVE_MODE',
                        'is_bool' => true,
                        'desc' => $this->l('Enable or disable logging of customer search queries.'),
                        'values' => array(
                            array(
                                'id' => 'active_on',
                                'value' => true,
                                'label' => $this->l('Enabled')
                            ),
                            array(
                                'id' => 'active_off',
                                'value' => false,
                                'label' => $this->l('Disabled')
                            )
                        ),
                    ),
                ),
                'submit' => array(
                    'title' => $this->l('Save'),
                ),
            ),
        );
    }

    /**
     * Set values for the inputs of the form.
     */
    protected function getConfigFormValues()
    {
        return array(
            'SEARCHLOG_LIVE_MODE' => Configuration::get('SEARCHLOG_LIVE_MODE', false),
        );
    }

    /**
     * Save form configuration.
     */
    protected function postProcess()
    {
        $form_values = $this->getConfigFormValues();

        foreach (array_keys($form_values) as $key) {
            Configuration::updateValue($key, Tools::getValue($key));
        }
    }

    /**
     * Add the CSS & JavaScript files you want to be loaded in the BO.
     */
    public function hookDisplayBackOfficeHeader()
    {
        if (Tools::getValue('module_name') == $this->name) {
            $this->context->controller->addJS($this->_path . 'views/js/back.js');
            $this->context->controller->addCSS($this->_path . 'views/css/back.css');
        }
    }

    /**
     * Add the CSS & JavaScript files you want to be added on the FO.
     */
    public function hookDisplayHeader()
    {
        $this->context->controller->addJS($this->_path . '/views/js/front.js');
        $this->context->controller->addCSS($this->_path . '/views/css/front.css');
    }

    /**
     * Hook that is executed after a search query.
     * This is where the search term and results are logged.
     */
    public function hookActionSearch($params)
    {
        if (!Configuration::get('SEARCHLOG_LIVE_MODE')) {
            return;
        }

        $keyword = pSQL($params['expr']);
        $results = (int)$params['total'];

        if (empty($keyword)) {
            return;
        }

        $db = Db::getInstance();
        $query = 'SELECT `id_slog`, `counter` FROM `' . _DB_PREFIX_ . 'slog` WHERE `keyword` = \'' . $keyword . '\'';
        $existing_log = $db->getRow($query);

        if ($existing_log) {
            // Update existing log entry
            $db->update(
                'slog',
                array(
                    'counter' => (int)$existing_log['counter'] + 1,
                    'results' => $results,
                    'date_upd' => date('Y-m-d H:i:s'),
                ),
                '`id_slog` = ' . (int)$existing_log['id_slog']
            );
        } else {
            // Insert new log entry
            $db->insert(
                'slog',
                array(
                    'keyword' => $keyword,
                    'results' => $results,
                    'counter' => 1,
                    'date_add' => date('Y-m-d H:i:s'),
                    'date_upd' => date('Y-m-d H:i:s'),
                )
            );
        }
    }

    /**
     * Create the database table for search logs.
     */
    protected function createSlogTable()
    {
        $sql = 'CREATE TABLE IF NOT EXISTS `' . _DB_PREFIX_ . 'slog` (
            `id_slog` INT(10) UNSIGNED NOT NULL AUTO_INCREMENT,
            `keyword` VARCHAR(255) NOT NULL,
            `results` INT(10) UNSIGNED NOT NULL DEFAULT 0,
            `counter` INT(10) UNSIGNED NOT NULL DEFAULT 1,
            `date_add` DATETIME NOT NULL,
            `date_upd` DATETIME NOT NULL,
            PRIMARY KEY (`id_slog`),
            UNIQUE KEY `keyword` (`keyword`)
        ) ENGINE=' . _MYSQL_ENGINE_ . ' DEFAULT CHARSET=utf8;';

        return Db::getInstance()->execute($sql);
    }

    /**
     * Drop the database table for search logs.
     */
    protected function dropSlogTable()
    {
        $sql = 'DROP TABLE IF EXISTS `' . _DB_PREFIX_ . 'slog`';

        return Db::getInstance()->execute($sql);
    }

    /**
     * Install a new tab in the Back Office for managing search logs.
     */
    protected function installTab()
    {
        $tab = new Tab();
        $tab->class_name = 'AdminSlog';
        $tab->module = $this->name;
        $tab->id_parent = (int)Tab::getIdFromClassName('ShopParameters'); // Or 'AdvancedParameters' for older PS versions
        $tab->active = 1;
        foreach (Language::getLanguages(true) as $lang) {
            $tab->name[$lang['id_lang']] = $this->l('Search Log');
        }
        return $tab->add();
    }

    /**
     * Uninstall the Back Office tab.
     */
    protected function uninstallTab()
    {
        $id_tab = (int)Tab::getIdFromClassName('AdminSlog');
        if ($id_tab) {
            $tab = new Tab($id_tab);
            return $tab->delete();
        }
        return true;
    }
}
```
```json
{
  "name": "Log di ricerca",
  "description": "Registra le query di ricerca dei clienti sul tuo negozio PrestaShop.",
  "version": "1.0.0",
  "author": "MyPresta.eu",
  "tab": "administration",
  "is_configurable": 1,
  "ps_versions_compliancy": {
    "min": "1.6.0.0",
    "max": "9.0.0.0"
  },
  "php_versions_compliancy": {
    "min": "5.6",
    "max": "8.5"
  }
}
```

## 4. 8 Classe del modulo (`searchlog.php`)

Questo è il file della classe principale del modulo, `searchlog.php`. Contiene la logica principale per l'installazione, la disinstallazione, la configurazione e le implementazioni degli hook.

```php
<?php
/**
 * 2007-2024 PrestaShop
 *
 * NOTICE OF LICENSE
 *
 * This source file is subject to the Academic Free License (AFL 3.0)
 * that is bundled with this package in the file LICENSE.txt.
 * It is also available through the world-wide-web at this URL:
 * http://opensource.org/licenses/afl-3.0.php
 * If you did not receive a copy of the license and are unable to
 * obtain it through the world-wide-web, please send an email
 * to license@prestashop.com so we can send you a copy immediately.
 *
 * DISCLAIMER
 *
 * Do not edit or add to this file if you wish to upgrade PrestaShop to newer
 * versions in the future. If you wish to customize PrestaShop for your
 * needs please refer to http://www.prestashop.com for more information.
 *
 * @author    PrestaShop SA <contact@prestashop.com>
 * @copyright 2007-2024 PrestaShop SA
 * @license   http://opensource.org/licenses/afl-3.0.php  Academic Free License (AFL 3.0)
 * International Registered Trademark & Property of PrestaShop SA
 */

if (!defined('_PS_VERSION_')) {
    exit;
}

class Searchlog extends Module
{
    protected $config_form = false;

    public function __construct()
    {
        $this->name = 'searchlog';
        $this->tab = 'administration';
        $this->version = '1.0.0';
        $this->author = 'MyPresta.eu';
        $this->need_instance = 0;

        /**
         * Set $this->bootstrap to true if your module is compliant with bootstrap (PrestaShop 1.6)
         */
        $this->bootstrap = true;

        parent::__construct();

        $this->displayName = $this->l('Log di ricerca');
        $this->description = $this->l('Registra le query di ricerca dei clienti sul tuo negozio PrestaShop.');

        $this->ps_versions_compliancy = array('min' => '1.6', 'max' => _PS_VERSION_);
    }

    /**
     * Don't forget to create update methods if needed:
     * http://doc.prestashop.com/display/PS16/Enabling+the+Auto-Update
     */
    public function install()
    {
        if (parent::install() &&
            $this->registerHook('displayHeader') &&
            $this->registerHook('displayBackOfficeHeader') &&
            $this->registerHook('actionSearch') &&
            $this->registerHook('actionModuleInstall') &&
            $this->registerHook('actionModuleUninstall') &&
            $this->installTab() &&
            $this->createSlogTable()
        ) {
            Configuration::updateValue('SEARCHLOG_LIVE_MODE', false);
            return true;
        }
        return false;
    }

    public function uninstall()
    {
        if (!parent::uninstall() ||
            !Configuration::deleteByName('SEARCHLOG_LIVE_MODE') ||
            !$this->uninstallTab() ||
            !$this->dropSlogTable()
        ) {
            return false;
        }
        return true;
    }

    /**
     * Load the configuration form
     */
    public function getContent()
    {
        /**
         * If values have been submitted in the form, process them.
         */
        if (((bool)Tools::isSubmit('submitSearchlogModule')) == true) {
            $this->postProcess();
        }

        $this->context->smarty->assign('module_dir', $this->_path);

        $output = $this->context->smarty->fetch($this->local_path . 'views/templates/admin/configure.tpl');

        return $output . $this->renderForm();
    }

    /**
     * Create the form that will be displayed in the configuration of your module.
     */
    protected function renderForm()
    {
        $helper = new HelperForm();

        $helper->show_toolbar = false;
        $helper->table = $this->table;
        $helper->module = $this;
        $helper->default_form_language = $this->context->language->id;
        $helper->allow_employee_form_lang = Configuration::get('PS_BO_ALLOW_EMPLOYEE_FORM_LANG', 0);

        $helper->identifier = $this->identifier;
        $helper->submit_action = 'submitSearchlogModule';
        $helper->currentIndex = $this->context->link->getAdminLink('AdminModules', false)
            . '&configure=' . $this->name . '&tab_module=' . $this->tab . '&module_name=' . $this->name;
        $helper->token = Tools::getAdminTokenLite('AdminModules');

        $helper->tpl_vars = array(
            'fields_value' => $this->getConfigFormValues(), /* Add values for your inputs */
            'languages' => $this->context->controller->getLanguages(),
            'id_language' => $this->context->language->id,
        );

        return $helper->generateForm(array($this->getConfigForm()));
    }

    /**
     * Create the structure of your form.
     */
    protected function getConfigForm()
    {
        return array(
            'form' => array(
                'legend' => array(
                    'title' => $this->l('Impostazioni'),
                    'icon' => 'icon-cogs',
                ),
                'input' => array(
                    array(
                        'type' => 'switch',
                        'label' => $this->l('Abilita Log di ricerca'),
                        'name' => 'SEARCHLOG_LIVE_MODE',
                        'is_bool' => true,
                        'desc' => $this->l('Abilita o disabilita la registrazione delle query di ricerca dei clienti.'),
                        'values' => array(
                            array(
                                'id' => 'active_on',
                                'value' => true,
                                'label' => $this->l('Abilitato')
                            ),
                            array(
                                'id' => 'active_off',
                                'value' => false,
                                'label' => $this->l('Disabilitato')
                            )
                        ),
                    ),
                ),
                'submit' => array(
                    'title' => $this->l('Salva'),
                ),
            ),
        );
    }

    /**
     * Set values for the inputs of the form.
     */
    protected function getConfigFormValues()
    {
        return array(
            'SEARCHLOG_LIVE_MODE' => Configuration::get('SEARCHLOG_LIVE_MODE', false),
        );
    }

    /**
     * Save form configuration.
     */
    protected function postProcess()
    {
        $form_values = $this->getConfigFormValues();

        foreach (array_keys($form_values) as $key) {
            Configuration::updateValue($key, Tools::getValue($key));
        }
    }

    /**
     * Add the CSS & JavaScript files you want to be loaded in the BO.
     */
    public function hookDisplayBackOfficeHeader()
    {
        if (Tools::getValue('module_name') == $this->name) {
            $this->context->controller->addJS($this->_path . 'views/js/back.js');
            $this->context->controller->addCSS($this->_path . 'views/css/back.css');
        }
    }

    /**
     * Add the CSS & JavaScript files you want to be added on the FO.
     */
    public function hookDisplayHeader()
    {
        $this->context->controller->addJS($this->_path . '/views/js/front.js');
        $this->context->controller->addCSS($this->_path . '/views/css/front.css');
    }

    /**
     * Hook that is executed after a search query.
     * This is where the search term and results are logged.
     */
    public function hookActionSearch($params)
    {
        if (!Configuration::get('SEARCHLOG_LIVE_MODE')) {
            return;
        }

        $keyword = pSQL($params['expr']);
        $results = (int)$params['total'];

        if (empty($keyword)) {
            return;
        }

        $db = Db::getInstance();
        $query = 'SELECT `id_slog`, `counter` FROM `' . _DB_PREFIX_ . 'slog` WHERE `keyword` = \'' . $keyword . '\'';
        $existing_log = $db->getRow($query);

        if ($existing_log) {
            // Update existing log entry
            $db->update(
                'slog',
                array(
                    'counter' => (int)$existing_log['counter'] + 1,
                    'results' => $results,
                    'date_upd' => date('Y-m-d H:i:s'),
                ),
                '`id_slog` = ' . (int)$existing_log['id_slog']
            );
        } else {
            // Insert new log entry
            $db->insert(
                'slog',
                array(
                    'keyword' => $keyword,
                    'results' => $results,
                    'counter' => 1,
                    'date_add' => date('Y-m-d H:i:s'),
                    'date_upd' => date('Y-m-d H:i:s'),
                )
            );
        }
    }

    /**
     * Create the database table for search logs.
     */
    protected function createSlogTable()
    {
        $sql = 'CREATE TABLE IF NOT EXISTS `' . _DB_PREFIX_ . 'slog` (
            `id_slog` INT(10) UNSIGNED NOT NULL AUTO_INCREMENT,
            `keyword` VARCHAR(255) NOT NULL,
            `results` INT(10) UNSIGNED NOT NULL DEFAULT 0,
            `counter` INT(10) UNSIGNED NOT NULL DEFAULT 1,
            `date_add` DATETIME NOT NULL,
            `date_upd` DATETIME NOT NULL,
            PRIMARY KEY (`id_slog`),
            UNIQUE KEY `keyword` (`keyword`)
        ) ENGINE=' . _MYSQL_ENGINE_ . ' DEFAULT CHARSET=utf8;';

        return Db::getInstance()->execute($sql);
    }

    /**
     * Drop the database table for search logs.
     */
    protected function dropSlogTable()
    {
        $sql = 'DROP TABLE IF EXISTS `' . _DB_PREFIX_ . 'slog`';

        return Db::getInstance()->execute($sql);
    }

    /**
     * Install a new tab in the Back Office for managing search logs.
     */
    protected function installTab()
    {
        $tab = new Tab();
        $tab->class_name = 'AdminSlog';
        $tab->module = $this->name;
        $tab->id_parent = (int)Tab::getIdFromClassName('ShopParameters'); // Or 'AdvancedParameters' for older PS versions
        $tab->active = 1;
        foreach (Language::getLanguages(true) as $lang) {
            $tab->name[$lang['id_lang']] = $this->l('Log di ricerca');
        }
        return $tab->add();
    }

    /**
     * Uninstall the Back Office tab.
     */
    protected function uninstallTab()
    {
        $id_tab = (int)Tab::getIdFromClassName('AdminSlog');
        if ($id_tab) {
            $tab = new Tab($id_tab);
            return $tab->delete();
        }
        return true;
    }
}
