Yet Another Framework
=====================

**Table of Contents**

-   [Introduction](/intro/yaf.html)
-   [Installing/Configuring](/yaf/setup.html)
    -   [Requirements](/yaf/setup.html#Requirements)
    -   [Installation](/yaf/setup.html#Installation)
    -   [Runtime Configuration](/yaf/setup.html#Runtime%20Configuration)
    -   [Resource Types](/yaf/setup.html#Resource%20Types)
-   [Predefined Constants](/yaf/constants.html)
-   [Examples](/yaf/tutorials.html)
-   [Application Configuration](/yaf/appconfig.html)
-   [Yaf\_Application](/class/yaf-application.html) — The
    Yaf\_Application class
    -   [Yaf\_Application::app](/class/yaf-application.html#Yaf_Application::app)
        — Retrieve an Application instance
    -   [Yaf\_Application::bootstrap](/class/yaf-application.html#Yaf_Application::bootstrap)
        — Call bootstrap
    -   [Yaf\_Application::clearLastError](/class/yaf-application.html#Yaf_Application::clearLastError)
        — Clear the last error info
    -   [Yaf\_Application::\_\_construct](/class/yaf-application.html#Yaf_Application::__construct)
        — Yaf\_Application constructor
    -   [Yaf\_Application::\_\_destruct](/class/yaf-application.html#Yaf_Application::__destruct)
        — The \_\_destruct purpose
    -   [Yaf\_Application::environ](/class/yaf-application.html#Yaf_Application::environ)
        — Retrive environ
    -   [Yaf\_Application::execute](/class/yaf-application.html#Yaf_Application::execute)
        — Execute a callback
    -   [Yaf\_Application::getAppDirectory](/class/yaf-application.html#Yaf_Application::getAppDirectory)
        — Get the application directory
    -   [Yaf\_Application::getConfig](/class/yaf-application.html#Yaf_Application::getConfig)
        — Retrive the config instance
    -   [Yaf\_Application::getDispatcher](/class/yaf-application.html#Yaf_Application::getDispatcher)
        — Get Yaf\_Dispatcher instance
    -   [Yaf\_Application::getLastErrorMsg](/class/yaf-application.html#Yaf_Application::getLastErrorMsg)
        — Get message of the last occurred error
    -   [Yaf\_Application::getLastErrorNo](/class/yaf-application.html#Yaf_Application::getLastErrorNo)
        — Get code of last occurred error
    -   [Yaf\_Application::getModules](/class/yaf-application.html#Yaf_Application::getModules)
        — Get defined module names
    -   [Yaf\_Application::run](/class/yaf-application.html#Yaf_Application::run)
        — Start Yaf\_Application
    -   [Yaf\_Application::setAppDirectory](/class/yaf-application.html#Yaf_Application::setAppDirectory)
        — Change the application directory
-   [Yaf\_Bootstrap\_Abstract](/class/yaf-bootstrap-abstract.html) — The
    Yaf\_Bootstrap\_Abstract class
-   [Yaf\_Dispatcher](/class/yaf-dispatcher.html) — The Yaf\_Dispatcher
    class
    -   [Yaf\_Dispatcher::autoRender](/class/yaf-dispatcher.html#Yaf_Dispatcher::autoRender)
        — Switch on/off autorendering
    -   [Yaf\_Dispatcher::catchException](/class/yaf-dispatcher.html#Yaf_Dispatcher::catchException)
        — Switch on/off exception catching
    -   [Yaf\_Dispatcher::\_\_construct](/class/yaf-dispatcher.html#Yaf_Dispatcher::__construct)
        — Yaf\_Dispatcher constructor
    -   [Yaf\_Dispatcher::disableView](/class/yaf-dispatcher.html#Yaf_Dispatcher::disableView)
        — Disable view rendering
    -   [Yaf\_Dispatcher::dispatch](/class/yaf-dispatcher.html#Yaf_Dispatcher::dispatch)
        — Dispatch a request
    -   [Yaf\_Dispatcher::enableView](/class/yaf-dispatcher.html#Yaf_Dispatcher::enableView)
        — Enable view rendering
    -   [Yaf\_Dispatcher::flushInstantly](/class/yaf-dispatcher.html#Yaf_Dispatcher::flushInstantly)
        — Switch on/off the instant flushing
    -   [Yaf\_Dispatcher::getApplication](/class/yaf-dispatcher.html#Yaf_Dispatcher::getApplication)
        — Retrive the application
    -   [Yaf\_Dispatcher::getDefaultAction](/class/yaf-dispatcher.html#Yaf_Dispatcher::getDefaultAction)
        — Retrive the default action name
    -   [Yaf\_Dispatcher::getDefaultController](/class/yaf-dispatcher.html#Yaf_Dispatcher::getDefaultController)
        — Retrive the default controller name
    -   [Yaf\_Dispatcher::getDefaultModule](/class/yaf-dispatcher.html#Yaf_Dispatcher::getDefaultModule)
        — Retrive the default module name
    -   [Yaf\_Dispatcher::getInstance](/class/yaf-dispatcher.html#Yaf_Dispatcher::getInstance)
        — Retrive the dispatcher instance
    -   [Yaf\_Dispatcher::getRequest](/class/yaf-dispatcher.html#Yaf_Dispatcher::getRequest)
        — Retrive the request instance
    -   [Yaf\_Dispatcher::getRouter](/class/yaf-dispatcher.html#Yaf_Dispatcher::getRouter)
        — Retrive router instance
    -   [Yaf\_Dispatcher::initView](/class/yaf-dispatcher.html#Yaf_Dispatcher::initView)
        — Initialize view and return it
    -   [Yaf\_Dispatcher::registerPlugin](/class/yaf-dispatcher.html#Yaf_Dispatcher::registerPlugin)
        — Register a plugin
    -   [Yaf\_Dispatcher::returnResponse](/class/yaf-dispatcher.html#Yaf_Dispatcher::returnResponse)
        — The returnResponse purpose
    -   [Yaf\_Dispatcher::setDefaultAction](/class/yaf-dispatcher.html#Yaf_Dispatcher::setDefaultAction)
        — Change default action name
    -   [Yaf\_Dispatcher::setDefaultController](/class/yaf-dispatcher.html#Yaf_Dispatcher::setDefaultController)
        — Change default controller name
    -   [Yaf\_Dispatcher::setDefaultModule](/class/yaf-dispatcher.html#Yaf_Dispatcher::setDefaultModule)
        — Change default module name
    -   [Yaf\_Dispatcher::setErrorHandler](/class/yaf-dispatcher.html#Yaf_Dispatcher::setErrorHandler)
        — Set error handler
    -   [Yaf\_Dispatcher::setRequest](/class/yaf-dispatcher.html#Yaf_Dispatcher::setRequest)
        — The setRequest purpose
    -   [Yaf\_Dispatcher::setView](/class/yaf-dispatcher.html#Yaf_Dispatcher::setView)
        — Set a custom view engine
    -   [Yaf\_Dispatcher::throwException](/class/yaf-dispatcher.html#Yaf_Dispatcher::throwException)
        — Switch on/off exception throwing
-   [Yaf\_Config\_Abstract](/class/yaf-config-abstract.html) — The
    Yaf\_Config\_Abstract class
    -   [Yaf\_Config\_Abstract::get](/class/yaf-config-abstract.html#Yaf_Config_Abstract::get)
        — Getter
    -   [Yaf\_Config\_Abstract::readonly](/class/yaf-config-abstract.html#Yaf_Config_Abstract::readonly)
        — Find a config whether readonly
    -   [Yaf\_Config\_Abstract::set](/class/yaf-config-abstract.html#Yaf_Config_Abstract::set)
        — Setter
    -   [Yaf\_Config\_Abstract::toArray](/class/yaf-config-abstract.html#Yaf_Config_Abstract::toArray)
        — Cast to array
-   [Yaf\_Config\_Ini](/class/yaf-config-ini.html) — The
    Yaf\_Config\_Ini class
    -   [Yaf\_Config\_Ini::\_\_construct](/class/yaf-config-ini.html#Yaf_Config_Ini::__construct)
        — Yaf\_Config\_Ini constructor
    -   [Yaf\_Config\_Ini::count](/class/yaf-config-ini.html#Yaf_Config_Ini::count)
        — Count all elements in Yaf\_Config.ini
    -   [Yaf\_Config\_Ini::current](/class/yaf-config-ini.html#Yaf_Config_Ini::current)
        — Retrieve the current value
    -   [Yaf\_Config\_Ini::\_\_get](/class/yaf-config-ini.html#Yaf_Config_Ini::__get)
        — Retrieve a element
    -   [Yaf\_Config\_Ini::\_\_isset](/class/yaf-config-ini.html#Yaf_Config_Ini::__isset)
        — Determine if a key is exists
    -   [Yaf\_Config\_Ini::key](/class/yaf-config-ini.html#Yaf_Config_Ini::key)
        — Fetch current element's key
    -   [Yaf\_Config\_Ini::next](/class/yaf-config-ini.html#Yaf_Config_Ini::next)
        — Advance the internal pointer
    -   [Yaf\_Config\_Ini::offsetExists](/class/yaf-config-ini.html#Yaf_Config_Ini::offsetExists)
        — The offsetExists purpose
    -   [Yaf\_Config\_Ini::offsetGet](/class/yaf-config-ini.html#Yaf_Config_Ini::offsetGet)
        — The offsetGet purpose
    -   [Yaf\_Config\_Ini::offsetSet](/class/yaf-config-ini.html#Yaf_Config_Ini::offsetSet)
        — The offsetSet purpose
    -   [Yaf\_Config\_Ini::offsetUnset](/class/yaf-config-ini.html#Yaf_Config_Ini::offsetUnset)
        — The offsetUnset purpose
    -   [Yaf\_Config\_Ini::readonly](/class/yaf-config-ini.html#Yaf_Config_Ini::readonly)
        — The readonly purpose
    -   [Yaf\_Config\_Ini::rewind](/class/yaf-config-ini.html#Yaf_Config_Ini::rewind)
        — The rewind purpose
    -   [Yaf\_Config\_Ini::\_\_set](/class/yaf-config-ini.html#Yaf_Config_Ini::__set)
        — The \_\_set purpose
    -   [Yaf\_Config\_Ini::toArray](/class/yaf-config-ini.html#Yaf_Config_Ini::toArray)
        — Return config as a PHP array
    -   [Yaf\_Config\_Ini::valid](/class/yaf-config-ini.html#Yaf_Config_Ini::valid)
        — The valid purpose
-   [Yaf\_Config\_Simple](/class/yaf-config-simple.html) — The
    Yaf\_Config\_Simple class
    -   [Yaf\_Config\_Simple::\_\_construct](/class/yaf-config-simple.html#Yaf_Config_Simple::__construct)
        — The \_\_construct purpose
    -   [Yaf\_Config\_Simple::count](/class/yaf-config-simple.html#Yaf_Config_Simple::count)
        — The count purpose
    -   [Yaf\_Config\_Simple::current](/class/yaf-config-simple.html#Yaf_Config_Simple::current)
        — The current purpose
    -   [Yaf\_Config\_Simple::\_\_get](/class/yaf-config-simple.html#Yaf_Config_Simple::__get)
        — The \_\_get purpose
    -   [Yaf\_Config\_Simple::\_\_isset](/class/yaf-config-simple.html#Yaf_Config_Simple::__isset)
        — The \_\_isset purpose
    -   [Yaf\_Config\_Simple::key](/class/yaf-config-simple.html#Yaf_Config_Simple::key)
        — The key purpose
    -   [Yaf\_Config\_Simple::next](/class/yaf-config-simple.html#Yaf_Config_Simple::next)
        — The next purpose
    -   [Yaf\_Config\_Simple::offsetExists](/class/yaf-config-simple.html#Yaf_Config_Simple::offsetExists)
        — The offsetExists purpose
    -   [Yaf\_Config\_Simple::offsetGet](/class/yaf-config-simple.html#Yaf_Config_Simple::offsetGet)
        — The offsetGet purpose
    -   [Yaf\_Config\_Simple::offsetSet](/class/yaf-config-simple.html#Yaf_Config_Simple::offsetSet)
        — The offsetSet purpose
    -   [Yaf\_Config\_Simple::offsetUnset](/class/yaf-config-simple.html#Yaf_Config_Simple::offsetUnset)
        — The offsetUnset purpose
    -   [Yaf\_Config\_Simple::readonly](/class/yaf-config-simple.html#Yaf_Config_Simple::readonly)
        — The readonly purpose
    -   [Yaf\_Config\_Simple::rewind](/class/yaf-config-simple.html#Yaf_Config_Simple::rewind)
        — The rewind purpose
    -   [Yaf\_Config\_Simple::\_\_set](/class/yaf-config-simple.html#Yaf_Config_Simple::__set)
        — The \_\_set purpose
    -   [Yaf\_Config\_Simple::toArray](/class/yaf-config-simple.html#Yaf_Config_Simple::toArray)
        — Returns a PHP array
    -   [Yaf\_Config\_Simple::valid](/class/yaf-config-simple.html#Yaf_Config_Simple::valid)
        — The valid purpose
-   [Yaf\_Controller\_Abstract](/class/yaf-controller-abstract.html) —
    The Yaf\_Controller\_Abstract class
    -   [Yaf\_Controller\_Abstract::\_\_construct](/class/yaf-controller-abstract.html#Yaf_Controller_Abstract::__construct)
        — Yaf\_Controller\_Abstract constructor
    -   [Yaf\_Controller\_Abstract::display](/class/yaf-controller-abstract.html#Yaf_Controller_Abstract::display)
        — The display purpose
    -   [Yaf\_Controller\_Abstract::forward](/class/yaf-controller-abstract.html#Yaf_Controller_Abstract::forward)
        — Foward to another action
    -   [Yaf\_Controller\_Abstract::getInvokeArg](/class/yaf-controller-abstract.html#Yaf_Controller_Abstract::getInvokeArg)
        — The getInvokeArg purpose
    -   [Yaf\_Controller\_Abstract::getInvokeArgs](/class/yaf-controller-abstract.html#Yaf_Controller_Abstract::getInvokeArgs)
        — The getInvokeArgs purpose
    -   [Yaf\_Controller\_Abstract::getModuleName](/class/yaf-controller-abstract.html#Yaf_Controller_Abstract::getModuleName)
        — Get module name
    -   [Yaf\_Controller\_Abstract::getName](/class/yaf-controller-abstract.html#Yaf_Controller_Abstract::getName)
        — Get self name
    -   [Yaf\_Controller\_Abstract::getRequest](/class/yaf-controller-abstract.html#Yaf_Controller_Abstract::getRequest)
        — Retrieve current request object
    -   [Yaf\_Controller\_Abstract::getResponse](/class/yaf-controller-abstract.html#Yaf_Controller_Abstract::getResponse)
        — Retrieve current response object
    -   [Yaf\_Controller\_Abstract::getView](/class/yaf-controller-abstract.html#Yaf_Controller_Abstract::getView)
        — Retrieve the view engine
    -   [Yaf\_Controller\_Abstract::getViewpath](/class/yaf-controller-abstract.html#Yaf_Controller_Abstract::getViewpath)
        — The getViewpath purpose
    -   [Yaf\_Controller\_Abstract::init](/class/yaf-controller-abstract.html#Yaf_Controller_Abstract::init)
        — Controller initializer
    -   [Yaf\_Controller\_Abstract::initView](/class/yaf-controller-abstract.html#Yaf_Controller_Abstract::initView)
        — The initView purpose
    -   [Yaf\_Controller\_Abstract::redirect](/class/yaf-controller-abstract.html#Yaf_Controller_Abstract::redirect)
        — Redirect to a URL
    -   [Yaf\_Controller\_Abstract::render](/class/yaf-controller-abstract.html#Yaf_Controller_Abstract::render)
        — Render view template
    -   [Yaf\_Controller\_Abstract::setViewpath](/class/yaf-controller-abstract.html#Yaf_Controller_Abstract::setViewpath)
        — The setViewpath purpose
-   [Yaf\_Action\_Abstract](/class/yaf-action-abstract.html) — The
    Yaf\_Action\_Abstract class
    -   [Yaf\_Action\_Abstract::execute](/class/yaf-action-abstract.html#Yaf_Action_Abstract::execute)
        — Action entry point
    -   [Yaf\_Action\_Abstract::getController](/class/yaf-action-abstract.html#Yaf_Action_Abstract::getController)
        — Retrieve controller object
    -   [Yaf\_Action\_Abstract::getControllerName](/class/yaf-action-abstract.html#Yaf_Action_Abstract::getControllerName)
        — Get controller name
-   [Yaf\_View\_Interface](/class/yaf-view-interface.html) — The
    Yaf\_View\_Interface class
    -   [Yaf\_View\_Interface::assign](/class/yaf-view-interface.html#Yaf_View_Interface::assign)
        — Assign value to View engine
    -   [Yaf\_View\_Interface::display](/class/yaf-view-interface.html#Yaf_View_Interface::display)
        — Render and output a template
    -   [Yaf\_View\_Interface::getScriptPath](/class/yaf-view-interface.html#Yaf_View_Interface::getScriptPath)
        — The getScriptPath purpose
    -   [Yaf\_View\_Interface::render](/class/yaf-view-interface.html#Yaf_View_Interface::render)
        — Render a template
    -   [Yaf\_View\_Interface::setScriptPath](/class/yaf-view-interface.html#Yaf_View_Interface::setScriptPath)
        — The setScriptPath purpose
-   [Yaf\_View\_Simple](/class/yaf-view-simple.html) — The
    Yaf\_View\_Simple class
    -   [Yaf\_View\_Simple::assign](/class/yaf-view-simple.html#Yaf_View_Simple::assign)
        — Assign values
    -   [Yaf\_View\_Simple::assignRef](/class/yaf-view-simple.html#Yaf_View_Simple::assignRef)
        — The assignRef purpose
    -   [Yaf\_View\_Simple::clear](/class/yaf-view-simple.html#Yaf_View_Simple::clear)
        — Clear Assigned values
    -   [Yaf\_View\_Simple::\_\_construct](/class/yaf-view-simple.html#Yaf_View_Simple::__construct)
        — Constructor of Yaf\_View\_Simple
    -   [Yaf\_View\_Simple::display](/class/yaf-view-simple.html#Yaf_View_Simple::display)
        — Render and display
    -   [Yaf\_View\_Simple::eval](/class/yaf-view-simple.html#Yaf_View_Simple::eval)
        — Render template
    -   [Yaf\_View\_Simple::\_\_get](/class/yaf-view-simple.html#Yaf_View_Simple::__get)
        — Retrieve assigned variable
    -   [Yaf\_View\_Simple::getScriptPath](/class/yaf-view-simple.html#Yaf_View_Simple::getScriptPath)
        — Get templates directory
    -   [Yaf\_View\_Simple::\_\_isset](/class/yaf-view-simple.html#Yaf_View_Simple::__isset)
        — The \_\_isset purpose
    -   [Yaf\_View\_Simple::render](/class/yaf-view-simple.html#Yaf_View_Simple::render)
        — Render template
    -   [Yaf\_View\_Simple::\_\_set](/class/yaf-view-simple.html#Yaf_View_Simple::__set)
        — Set value to engine
    -   [Yaf\_View\_Simple::setScriptPath](/class/yaf-view-simple.html#Yaf_View_Simple::setScriptPath)
        — Set tempaltes directory
-   [Yaf\_Loader](/class/yaf-loader.html) — The Yaf\_Loader class
    -   [Yaf\_Loader::autoload](/class/yaf-loader.html#Yaf_Loader::autoload)
        — The autoload purpose
    -   [Yaf\_Loader::clearLocalNamespace](/class/yaf-loader.html#Yaf_Loader::clearLocalNamespace)
        — The clearLocalNamespace purpose
    -   [Yaf\_Loader::\_\_construct](/class/yaf-loader.html#Yaf_Loader::__construct)
        — The \_\_construct purpose
    -   [Yaf\_Loader::getInstance](/class/yaf-loader.html#Yaf_Loader::getInstance)
        — The getInstance purpose
    -   [Yaf\_Loader::getLibraryPath](/class/yaf-loader.html#Yaf_Loader::getLibraryPath)
        — Get the library path
    -   [Yaf\_Loader::getLocalNamespace](/class/yaf-loader.html#Yaf_Loader::getLocalNamespace)
        — The getLocalNamespace purpose
    -   [Yaf\_Loader::getNamespacePath](/class/yaf-loader.html#Yaf_Loader::getNamespacePath)
        — Retieve path of a registered namespace
    -   [Yaf\_Loader::getLocalNamespace](/class/yaf-loader.html#Yaf_Loader::getLocalNamespace)
        — Retrive all register namespaces info
    -   [Yaf\_Loader::import](/class/yaf-loader.html#Yaf_Loader::import)
        — The import purpose
    -   [Yaf\_Loader::isLocalName](/class/yaf-loader.html#Yaf_Loader::isLocalName)
        — The isLocalName purpose
    -   [Yaf\_Loader::registerLocalNamespace](/class/yaf-loader.html#Yaf_Loader::registerLocalNamespace)
        — Register local class prefix
    -   [Yaf\_Loader::registerNamespace](/class/yaf-loader.html#Yaf_Loader::registerNamespace)
        — Register namespace with searching path
    -   [Yaf\_Loader::setLibraryPath](/class/yaf-loader.html#Yaf_Loader::setLibraryPath)
        — Change the library path
-   [Yaf\_Plugin\_Abstract](/class/yaf-plugin-abstract.html) — The
    Yaf\_Plugin\_Abstract class
    -   [Yaf\_Plugin\_Abstract::dispatchLoopShutdown](/class/yaf-plugin-abstract.html#Yaf_Plugin_Abstract::dispatchLoopShutdown)
        — The dispatchLoopShutdown purpose
    -   [Yaf\_Plugin\_Abstract::dispatchLoopStartup](/class/yaf-plugin-abstract.html#Yaf_Plugin_Abstract::dispatchLoopStartup)
        — Hook before dispatch loop
    -   [Yaf\_Plugin\_Abstract::postDispatch](/class/yaf-plugin-abstract.html#Yaf_Plugin_Abstract::postDispatch)
        — The postDispatch purpose
    -   [Yaf\_Plugin\_Abstract::preDispatch](/class/yaf-plugin-abstract.html#Yaf_Plugin_Abstract::preDispatch)
        — The preDispatch purpose
    -   [Yaf\_Plugin\_Abstract::preResponse](/class/yaf-plugin-abstract.html#Yaf_Plugin_Abstract::preResponse)
        — The preResponse purpose
    -   [Yaf\_Plugin\_Abstract::routerShutdown](/class/yaf-plugin-abstract.html#Yaf_Plugin_Abstract::routerShutdown)
        — The routerShutdown purpose
    -   [Yaf\_Plugin\_Abstract::routerStartup](/class/yaf-plugin-abstract.html#Yaf_Plugin_Abstract::routerStartup)
        — RouterStartup hook
-   [Yaf\_Registry](/class/yaf-registry.html) — The Yaf\_Registry class
    -   [Yaf\_Registry::\_\_construct](/class/yaf-registry.html#Yaf_Registry::__construct)
        — Yaf\_Registry implements singleton
    -   [Yaf\_Registry::del](/class/yaf-registry.html#Yaf_Registry::del)
        — Remove an item from registry
    -   [Yaf\_Registry::get](/class/yaf-registry.html#Yaf_Registry::get)
        — Retrieve an item from registry
    -   [Yaf\_Registry::has](/class/yaf-registry.html#Yaf_Registry::has)
        — Check whether an item exists
    -   [Yaf\_Registry::set](/class/yaf-registry.html#Yaf_Registry::set)
        — Add an item into registry
-   [Yaf\_Request\_Abstract](/class/yaf-request-abstract.html) — The
    Yaf\_Request\_Abstract class
    -   [Yaf\_Request\_Abstract::clearParams](/class/yaf-request-abstract.html#Yaf_Request_Abstract::clearParams)
        — Remove all params
    -   [Yaf\_Request\_Abstract::getActionName](/class/yaf-request-abstract.html#Yaf_Request_Abstract::getActionName)
        — The getActionName purpose
    -   [Yaf\_Request\_Abstract::getBaseUri](/class/yaf-request-abstract.html#Yaf_Request_Abstract::getBaseUri)
        — The getBaseUri purpose
    -   [Yaf\_Request\_Abstract::getControllerName](/class/yaf-request-abstract.html#Yaf_Request_Abstract::getControllerName)
        — The getControllerName purpose
    -   [Yaf\_Request\_Abstract::getEnv](/class/yaf-request-abstract.html#Yaf_Request_Abstract::getEnv)
        — Retrieve ENV varialbe
    -   [Yaf\_Request\_Abstract::getException](/class/yaf-request-abstract.html#Yaf_Request_Abstract::getException)
        — The getException purpose
    -   [Yaf\_Request\_Abstract::getLanguage](/class/yaf-request-abstract.html#Yaf_Request_Abstract::getLanguage)
        — Retrieve client's prefered language
    -   [Yaf\_Request\_Abstract::getMethod](/class/yaf-request-abstract.html#Yaf_Request_Abstract::getMethod)
        — Retrieve the request method
    -   [Yaf\_Request\_Abstract::getModuleName](/class/yaf-request-abstract.html#Yaf_Request_Abstract::getModuleName)
        — The getModuleName purpose
    -   [Yaf\_Request\_Abstract::getParam](/class/yaf-request-abstract.html#Yaf_Request_Abstract::getParam)
        — Retrieve calling parameter
    -   [Yaf\_Request\_Abstract::getParams](/class/yaf-request-abstract.html#Yaf_Request_Abstract::getParams)
        — Retrieve all calling parameters
    -   [Yaf\_Request\_Abstract::getRequestUri](/class/yaf-request-abstract.html#Yaf_Request_Abstract::getRequestUri)
        — The getRequestUri purpose
    -   [Yaf\_Request\_Abstract::getServer](/class/yaf-request-abstract.html#Yaf_Request_Abstract::getServer)
        — Retrieve SERVER variable
    -   [Yaf\_Request\_Abstract::isCli](/class/yaf-request-abstract.html#Yaf_Request_Abstract::isCli)
        — Determine if request is CLI request
    -   [Yaf\_Request\_Abstract::isDispatched](/class/yaf-request-abstract.html#Yaf_Request_Abstract::isDispatched)
        — Determin if the request is dispatched
    -   [Yaf\_Request\_Abstract::isGet](/class/yaf-request-abstract.html#Yaf_Request_Abstract::isGet)
        — Determine if request is GET request
    -   [Yaf\_Request\_Abstract::isHead](/class/yaf-request-abstract.html#Yaf_Request_Abstract::isHead)
        — Determine if request is HEAD request
    -   [Yaf\_Request\_Abstract::isOptions](/class/yaf-request-abstract.html#Yaf_Request_Abstract::isOptions)
        — Determine if request is OPTIONS request
    -   [Yaf\_Request\_Abstract::isPost](/class/yaf-request-abstract.html#Yaf_Request_Abstract::isPost)
        — Determine if request is POST request
    -   [Yaf\_Request\_Abstract::isPut](/class/yaf-request-abstract.html#Yaf_Request_Abstract::isPut)
        — Determine if request is PUT request
    -   [Yaf\_Request\_Abstract::isRouted](/class/yaf-request-abstract.html#Yaf_Request_Abstract::isRouted)
        — Determin if request has been routed
    -   [Yaf\_Request\_Abstract::isXmlHttpRequest](/class/yaf-request-abstract.html#Yaf_Request_Abstract::isXmlHttpRequest)
        — Determine if request is AJAX request
    -   [Yaf\_Request\_Abstract::setActionName](/class/yaf-request-abstract.html#Yaf_Request_Abstract::setActionName)
        — Set action name
    -   [Yaf\_Request\_Abstract::setBaseUri](/class/yaf-request-abstract.html#Yaf_Request_Abstract::setBaseUri)
        — Set base URI
    -   [Yaf\_Request\_Abstract::setControllerName](/class/yaf-request-abstract.html#Yaf_Request_Abstract::setControllerName)
        — Set controller name
    -   [Yaf\_Request\_Abstract::setDispatched](/class/yaf-request-abstract.html#Yaf_Request_Abstract::setDispatched)
        — The setDispatched purpose
    -   [Yaf\_Request\_Abstract::setModuleName](/class/yaf-request-abstract.html#Yaf_Request_Abstract::setModuleName)
        — Set module name
    -   [Yaf\_Request\_Abstract::setParam](/class/yaf-request-abstract.html#Yaf_Request_Abstract::setParam)
        — Set a calling parameter to a request
    -   [Yaf\_Request\_Abstract::setRequestUri](/class/yaf-request-abstract.html#Yaf_Request_Abstract::setRequestUri)
        — The setRequestUri purpose
    -   [Yaf\_Request\_Abstract::setRouted](/class/yaf-request-abstract.html#Yaf_Request_Abstract::setRouted)
        — The setRouted purpose
-   [Yaf\_Request\_Http](/class/yaf-request-http.html) — The
    Yaf\_Request\_Http class
    -   [Yaf\_Request\_Http::\_\_construct](/class/yaf-request-http.html#Yaf_Request_Http::__construct)
        — Constructor of Yaf\_Request\_Http
    -   [Yaf\_Request\_Http::get](/class/yaf-request-http.html#Yaf_Request_Http::get)
        — Retrieve variable from client
    -   [Yaf\_Request\_Http::getCookie](/class/yaf-request-http.html#Yaf_Request_Http::getCookie)
        — Retrieve Cookie variable
    -   [Yaf\_Request\_Http::getFiles](/class/yaf-request-http.html#Yaf_Request_Http::getFiles)
        — The getFiles purpose
    -   [Yaf\_Request\_Http::getPost](/class/yaf-request-http.html#Yaf_Request_Http::getPost)
        — Retrieve POST variable
    -   [Yaf\_Request\_Http::getQuery](/class/yaf-request-http.html#Yaf_Request_Http::getQuery)
        — Fetch a query parameter
    -   [Yaf\_Request\_Http::getRaw](/class/yaf-request-http.html#Yaf_Request_Http::getRaw)
        — Retrieve Raw request body
    -   [Yaf\_Request\_Http::getRequest](/class/yaf-request-http.html#Yaf_Request_Http::getRequest)
        — The getRequest purpose
    -   [Yaf\_Request\_Http::isXmlHttpRequest](/class/yaf-request-http.html#Yaf_Request_Http::isXmlHttpRequest)
        — Determin if request is Ajax Request
-   [Yaf\_Request\_Simple](/class/yaf-request-simple.html) — The
    Yaf\_Request\_Simple class
    -   [Yaf\_Request\_Simple::\_\_construct](/class/yaf-request-simple.html#Yaf_Request_Simple::__construct)
        — Constructor of Yaf\_Request\_Simple
    -   [Yaf\_Request\_Simple::get](/class/yaf-request-simple.html#Yaf_Request_Simple::get)
        — The get purpose
    -   [Yaf\_Request\_Simple::getCookie](/class/yaf-request-simple.html#Yaf_Request_Simple::getCookie)
        — The getCookie purpose
    -   [Yaf\_Request\_Simple::getFiles](/class/yaf-request-simple.html#Yaf_Request_Simple::getFiles)
        — The getFiles purpose
    -   [Yaf\_Request\_Simple::getPost](/class/yaf-request-simple.html#Yaf_Request_Simple::getPost)
        — The getPost purpose
    -   [Yaf\_Request\_Simple::getQuery](/class/yaf-request-simple.html#Yaf_Request_Simple::getQuery)
        — The getQuery purpose
    -   [Yaf\_Request\_Simple::getRequest](/class/yaf-request-simple.html#Yaf_Request_Simple::getRequest)
        — The getRequest purpose
    -   [Yaf\_Request\_Simple::isXmlHttpRequest](/class/yaf-request-simple.html#Yaf_Request_Simple::isXmlHttpRequest)
        — Determin if request is AJAX request
-   [Yaf\_Response\_Abstract](/class/yaf-response-abstract.html) — The
    Yaf\_Response\_Abstract class
    -   [Yaf\_Response\_Abstract::appendBody](/class/yaf-response-abstract.html#Yaf_Response_Abstract::appendBody)
        — Append to response body
    -   [Yaf\_Response\_Abstract::clearBody](/class/yaf-response-abstract.html#Yaf_Response_Abstract::clearBody)
        — Discard all exists response body
    -   [Yaf\_Response\_Abstract::clearHeaders](/class/yaf-response-abstract.html#Yaf_Response_Abstract::clearHeaders)
        — Discard all set headers
    -   [Yaf\_Response\_Abstract::\_\_construct](/class/yaf-response-abstract.html#Yaf_Response_Abstract::__construct)
        — The \_\_construct purpose
    -   [Yaf\_Response\_Abstract::\_\_destruct](/class/yaf-response-abstract.html#Yaf_Response_Abstract::__destruct)
        — The \_\_destruct purpose
    -   [Yaf\_Response\_Abstract::getBody](/class/yaf-response-abstract.html#Yaf_Response_Abstract::getBody)
        — Retrieve a exists content
    -   [Yaf\_Response\_Abstract::getHeader](/class/yaf-response-abstract.html#Yaf_Response_Abstract::getHeader)
        — The getHeader purpose
    -   [Yaf\_Response\_Abstract::prependBody](/class/yaf-response-abstract.html#Yaf_Response_Abstract::prependBody)
        — The prependBody purpose
    -   [Yaf\_Response\_Abstract::response](/class/yaf-response-abstract.html#Yaf_Response_Abstract::response)
        — Send response
    -   [Yaf\_Response\_Abstract::setAllHeaders](/class/yaf-response-abstract.html#Yaf_Response_Abstract::setAllHeaders)
        — The setAllHeaders purpose
    -   [Yaf\_Response\_Abstract::setBody](/class/yaf-response-abstract.html#Yaf_Response_Abstract::setBody)
        — Set content to response
    -   [Yaf\_Response\_Abstract::setHeader](/class/yaf-response-abstract.html#Yaf_Response_Abstract::setHeader)
        — Set reponse header
    -   [Yaf\_Response\_Abstract::setRedirect](/class/yaf-response-abstract.html#Yaf_Response_Abstract::setRedirect)
        — The setRedirect purpose
    -   [Yaf\_Response\_Abstract::\_\_toString](/class/yaf-response-abstract.html#Yaf_Response_Abstract::__toString)
        — Retrieve all bodys as string
-   [Yaf\_Route\_Interface](/class/yaf-route-interface.html) — The
    Yaf\_Route\_Interface class
    -   [Yaf\_Route\_Interface::assemble](/class/yaf-route-interface.html#Yaf_Route_Interface::assemble)
        — Assemble a request
    -   [Yaf\_Route\_Interface::route](/class/yaf-route-interface.html#Yaf_Route_Interface::route)
        — Route a request
-   [Yaf\_Route\_Map](/class/yaf-route-map.html) — The Yaf\_Route\_Map
    class
    -   [Yaf\_Route\_Map::assemble](/class/yaf-route-map.html#Yaf_Route_Map::assemble)
        — Assemble a url
    -   [Yaf\_Route\_Map::\_\_construct](/class/yaf-route-map.html#Yaf_Route_Map::__construct)
        — The \_\_construct purpose
    -   [Yaf\_Route\_Map::route](/class/yaf-route-map.html#Yaf_Route_Map::route)
        — The route purpose
-   [Yaf\_Route\_Regex](/class/yaf-route-regex.html) — The
    Yaf\_Route\_Regex class
    -   [Yaf\_Route\_Regex::assemble](/class/yaf-route-regex.html#Yaf_Route_Regex::assemble)
        — Assemble a url
    -   [Yaf\_Route\_Regex::\_\_construct](/class/yaf-route-regex.html#Yaf_Route_Regex::__construct)
        — Yaf\_Route\_Regex constructor
    -   [Yaf\_Route\_Regex::route](/class/yaf-route-regex.html#Yaf_Route_Regex::route)
        — The route purpose
-   [Yaf\_Route\_Rewrite](/class/yaf-route-rewrite.html) — The
    Yaf\_Route\_Rewrite class
    -   [Yaf\_Route\_Rewrite::assemble](/class/yaf-route-rewrite.html#Yaf_Route_Rewrite::assemble)
        — Assemble a url
    -   [Yaf\_Route\_Rewrite::\_\_construct](/class/yaf-route-rewrite.html#Yaf_Route_Rewrite::__construct)
        — Yaf\_Route\_Rewrite constructor
    -   [Yaf\_Route\_Rewrite::route](/class/yaf-route-rewrite.html#Yaf_Route_Rewrite::route)
        — The route purpose
-   [Yaf\_Router](/class/yaf-router.html) — The Yaf\_Router class
    -   [Yaf\_Router::addConfig](/class/yaf-router.html#Yaf_Router::addConfig)
        — Add config-defined routes into Router
    -   [Yaf\_Router::addRoute](/class/yaf-router.html#Yaf_Router::addRoute)
        — Add new Route into Router
    -   [Yaf\_Router::\_\_construct](/class/yaf-router.html#Yaf_Router::__construct)
        — Yaf\_Router constructor
    -   [Yaf\_Router::getCurrentRoute](/class/yaf-router.html#Yaf_Router::getCurrentRoute)
        — Get the effective route name
    -   [Yaf\_Router::getRoute](/class/yaf-router.html#Yaf_Router::getRoute)
        — Retrieve a route by name
    -   [Yaf\_Router::getRoutes](/class/yaf-router.html#Yaf_Router::getRoutes)
        — Retrieve registered routes
    -   [Yaf\_Router::route](/class/yaf-router.html#Yaf_Router::route) —
        The route purpose
-   [Yaf\_Route\_Simple](/class/yaf-route-simple.html) — The
    Yaf\_Route\_Simple class
    -   [Yaf\_Route\_Simple::assemble](/class/yaf-route-simple.html#Yaf_Route_Simple::assemble)
        — Assemble a url
    -   [Yaf\_Route\_Simple::\_\_construct](/class/yaf-route-simple.html#Yaf_Route_Simple::__construct)
        — Yaf\_Route\_Simple constructor
    -   [Yaf\_Route\_Simple::route](/class/yaf-route-simple.html#Yaf_Route_Simple::route)
        — Route a request
-   [Yaf\_Route\_Static](/class/yaf-route-static.html) — The
    Yaf\_Route\_Static class
    -   [Yaf\_Route\_Static::assemble](/class/yaf-route-static.html#Yaf_Route_Static::assemble)
        — Assemble a url
    -   [Yaf\_Route\_Static::match](/class/yaf-route-static.html#Yaf_Route_Static::match)
        — The match purpose
    -   [Yaf\_Route\_Static::route](/class/yaf-route-static.html#Yaf_Route_Static::route)
        — Route a request
-   [Yaf\_Route\_Supervar](/class/yaf-route-supervar.html) — The
    Yaf\_Route\_Supervar class
    -   [Yaf\_Route\_Supervar::assemble](/class/yaf-route-supervar.html#Yaf_Route_Supervar::assemble)
        — Assemble a url
    -   [Yaf\_Route\_Supervar::\_\_construct](/class/yaf-route-supervar.html#Yaf_Route_Supervar::__construct)
        — The \_\_construct purpose
    -   [Yaf\_Route\_Supervar::route](/class/yaf-route-supervar.html#Yaf_Route_Supervar::route)
        — The route purpose
-   [Yaf\_Session](/class/yaf-session.html) — The Yaf\_Session class
    -   [Yaf\_Session::\_\_construct](/class/yaf-session.html#Yaf_Session::__construct)
        — Constructor of Yaf\_Session
    -   [Yaf\_Session::count](/class/yaf-session.html#Yaf_Session::count)
        — The count purpose
    -   [Yaf\_Session::current](/class/yaf-session.html#Yaf_Session::current)
        — The current purpose
    -   [Yaf\_Session::del](/class/yaf-session.html#Yaf_Session::del) —
        The del purpose
    -   [Yaf\_Session::\_\_get](/class/yaf-session.html#Yaf_Session::__get)
        — The \_\_get purpose
    -   [Yaf\_Session::getInstance](/class/yaf-session.html#Yaf_Session::getInstance)
        — The getInstance purpose
    -   [Yaf\_Session::has](/class/yaf-session.html#Yaf_Session::has) —
        The has purpose
    -   [Yaf\_Session::\_\_isset](/class/yaf-session.html#Yaf_Session::__isset)
        — The \_\_isset purpose
    -   [Yaf\_Session::key](/class/yaf-session.html#Yaf_Session::key) —
        The key purpose
    -   [Yaf\_Session::next](/class/yaf-session.html#Yaf_Session::next)
        — The next purpose
    -   [Yaf\_Session::offsetExists](/class/yaf-session.html#Yaf_Session::offsetExists)
        — The offsetExists purpose
    -   [Yaf\_Session::offsetGet](/class/yaf-session.html#Yaf_Session::offsetGet)
        — The offsetGet purpose
    -   [Yaf\_Session::offsetSet](/class/yaf-session.html#Yaf_Session::offsetSet)
        — The offsetSet purpose
    -   [Yaf\_Session::offsetUnset](/class/yaf-session.html#Yaf_Session::offsetUnset)
        — The offsetUnset purpose
    -   [Yaf\_Session::rewind](/class/yaf-session.html#Yaf_Session::rewind)
        — The rewind purpose
    -   [Yaf\_Session::\_\_set](/class/yaf-session.html#Yaf_Session::__set)
        — The \_\_set purpose
    -   [Yaf\_Session::start](/class/yaf-session.html#Yaf_Session::start)
        — The start purpose
    -   [Yaf\_Session::\_\_unset](/class/yaf-session.html#Yaf_Session::__unset)
        — The \_\_unset purpose
    -   [Yaf\_Session::valid](/class/yaf-session.html#Yaf_Session::valid)
        — The valid purpose
-   [Yaf\_Exception](/class/yaf-exception.html) — The Yaf\_Exception
    class
    -   [Yaf\_Exception::\_\_construct](/class/yaf-exception.html#Yaf_Exception::__construct)
        — The \_\_construct purpose
    -   [Yaf\_Exception::getPrevious](/class/yaf-exception.html#Yaf_Exception::getPrevious)
        — The getPrevious purpose
-   [Yaf\_Exception\_TypeError](/class/yaf-exception-typeerror.html) —
    The Yaf\_Exception\_TypeError class
-   [Yaf\_Exception\_StartupError](/class/yaf-exception-startuperror.html)
    — The Yaf\_Exception\_StartupError class
-   [Yaf\_Exception\_DispatchFailed](/class/yaf-exception-dispatchfailed.html)
    — The Yaf\_Exception\_DispatchFailed class
-   [Yaf\_Exception\_RouterFailed](/class/yaf-exception-routerfailed.html)
    — The Yaf\_Exception\_RouterFailed class
-   [Yaf\_Exception\_LoadFailed](/class/yaf-exception-loadfailed.html) —
    The Yaf\_Exception\_LoadFailed class
-   [Yaf\_Exception\_LoadFailed\_Module](/class/yaf-exception-loadfailed-module.html)
    — The Yaf\_Exception\_LoadFailed\_Module class
-   [Yaf\_Exception\_LoadFailed\_Controller](/class/yaf-exception-loadfailed-controller.html)
    — The Yaf\_Exception\_LoadFailed\_Controller class
-   [Yaf\_Exception\_LoadFailed\_Action](/class/yaf-exception-loadfailed-action.html)
    — The Yaf\_Exception\_LoadFailed\_Action class
-   [Yaf\_Exception\_LoadFailed\_View](/class/yaf-exception-loadfailed-view.html)
    — The Yaf\_Exception\_LoadFailed\_View class

Introduction
------------

<span class="classname">Yaf\_Application</span> provides a bootstrapping
facility for applications which provides reusable resources, common- and
module-based bootstrap classes and dependency checking.

> **Note**:
>
> <span class="classname">Yaf\_Application</span> implements the
> singleton pattern, and <span class="classname">Yaf\_Application</span>
> can not be serialized or unserialized which will cause problem when
> you try to use PHPUnit to write some test case for Yaf.
>
> You may use @backupGlobals annotation of PHPUnit to control the backup
> and restore operations for global variables. thus can solve this
> problem.

Class synopsis
--------------

**Yaf\_Application**

<span class="ooclass"> <span class="modifier">final</span> class
**Yaf\_Application** </span> {

/\* Properties \*/

<span class="modifier">protected</span> `$config` ;

<span class="modifier">protected</span> `$dispatcher` ;

<span class="modifier">protected</span> <span
class="modifier">static</span> `$_app` ;

<span class="modifier">protected</span> `$_modules` ;

<span class="modifier">protected</span> `$_running` ;

<span class="modifier">protected</span> `$_environ` ;

/\* Methods \*/

<span class="modifier">public</span> <span
class="modifier">static</span><span class="type">mixed</span> <span
class="methodname">app</span> ( <span class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">bootstrap</span> (\[ <span
class="methodparam"><span class="type">Yaf\_Bootstrap\_Abstract</span>
`$bootstrap`</span> \] )

<span class="modifier">public</span> <span
class="type">Yaf\_Application</span> <span
class="methodname">clearLastError</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> ( <span
class="methodparam"><span class="type">mixed</span> `$config`</span> \[,
<span class="methodparam"><span class="type">string</span>
`$envrion`</span> \] )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">\_\_destruct</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">environ</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">execute</span> ( <span
class="methodparam"><span class="type">callable</span> `$entry`</span> ,
<span class="methodparam"><span class="type">string</span> `$...`</span>
)

<span class="modifier">public</span> <span
class="type">Yaf\_Application</span> <span
class="methodname">getAppDirectory</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="type">Yaf\_Config\_Abstract</span> <span
class="methodname">getConfig</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="type">Yaf\_Dispatcher</span> <span
class="methodname">getDispatcher</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getLastErrorMsg</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getLastErrorNo</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">getModules</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">run</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="type">Yaf\_Application</span> <span
class="methodname">setAppDirectory</span> ( <span
class="methodparam"><span class="type">string</span> `$directory`</span>
)

}

Properties
----------

`config`  

`dispatcher`  

`_app`  

`_modules`  

`_running`  

`_environ`  

Yaf\_Application::app
=====================

Retrieve an Application instance

### Description

<span class="modifier">public</span> <span
class="modifier">static</span><span class="type">mixed</span> <span
class="methodname">Yaf\_Application::app</span> ( <span
class="methodparam">void</span> )

Retrieve the <span class="classname">Yaf\_Application</span> instance.
Alternatively, we also could use <span
class="methodname">Yaf\_Dispatcher::getApplication</span>.

### Parameters

This function has no parameters.

### Return Values

A Yaf\_Application instance, if no Yaf\_Application was initialized
before, **`NULL`** will be returned.

### See Also

-   <span class="methodname">Yaf\_Dispatcher::getApplication</span>

Yaf\_Application::bootstrap
===========================

Call bootstrap

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Application::bootstrap</span> (\[ <span
class="methodparam"><span class="type">Yaf\_Bootstrap\_Abstract</span>
`$bootstrap`</span> \] )

Run a Bootstrap, all the methods defined in the Bootstrap and named with
prefix "\_init" will be called according to their declaration order, if
the parameter bootstrap is not supplied, Yaf will look for a Bootstrap
under application.directory.

### Parameters

`bootstrap`  
A <span class="classname">Yaf\_Bootstrap\_Abstract</span> instance

### Return Values

<span class="classname">Yaf\_Application</span> instance

### Examples

**Example \#1 <span class="function">A Bootstrap</span>example**

``` php
<?php
/**
 * This file should be under the APPLICATION_PATH . "/application/"(which was defined in the config passed to Yaf_Application).
 * and named Bootstrap.php,  so the Yaf_Application can find it 
 */
class Bootstrap extends Yaf_Bootstrap_Abstract {
    function _initConfig(Yaf_Dispatcher $dispatcher) {
        echo "1st called\n";
    }

    function _initPlugin($dispatcher) {
        echo "2nd called\n";
    }
}
?>
```

**Example \#2 <span
class="function">Yaf\_Application::bootstrap</span>example**

``` php
<?php

defined('APPLICATION_PATH')                  // APPLICATION_PATH will be used in the ini config file
    || define('APPLICATION_PATH', __DIR__)); //__DIR__ was introduced after PHP 5.3

$application = new Yaf_Application(APPLICATION_PATH.'/conf/application.ini');
$application->bootstrap();
?>
```

The above example will output something similar to:

    1st called
    2nd called

### See Also

-   <span class="classname">Yaf\_Bootstrap\_Abstract</span>

Yaf\_Application::clearLastError
================================

Clear the last error info

### Description

<span class="modifier">public</span> <span
class="type">Yaf\_Application</span> <span
class="methodname">Yaf\_Application::clearLastError</span> ( <span
class="methodparam">void</span> )

### Parameters

This function has no parameters.

### Return Values

### Examples

**Example \#1 <span
class="function">Yaf\_Application::clearLastError</span>example**

``` php
<?php
function error_handler($errno, $errstr, $errfile, $errline) {
   Yaf_Application::app()->clearLastError();
   var_dump(Yaf_Application::app()->getLastErrorNo());
}
 
$config = array(                   
 "application" => array(
   "directory" => "/tmp/notexists",
     "dispatcher" => array(
       "throwException" => 0, //trigger error instead of throw exception when error occure
      ),
  ),
);
  
$app = new Yaf_Application($config);
$app->getDispatcher()->setErrorHandler("error_handler", E_RECOVERABLE_ERROR);
$app->run();
?>
```

The above example will output something similar to:

    int(0)

Yaf\_Application::\_\_construct
===============================

Yaf\_Application constructor

### Description

<span class="modifier">public</span> <span
class="methodname">Yaf\_Application::\_\_construct</span> ( <span
class="methodparam"><span class="type">mixed</span> `$config`</span> \[,
<span class="methodparam"><span class="type">string</span>
`$envrion`</span> \] )

Instance a <span class="classname">Yaf\_Application</span>.

### Parameters

`config`  
A ini config file path, or a config array

If is a ini config file, there should be a section named as the one
defined by <a href="/yaf/setup.html#" class="link">yaf.environ</a>,
which is "product" by default.

> **Note**:
>
> If you use a ini configuration file as your applicatioin's config
> container. you would open the
> <a href="/yaf/setup.html#" class="link">yaf.cache_config</a> to
> improve performance.

And the config entry(and there default value) list blow:

**Example \#1 A ini config file example**

``` ini
[product]
;this one should alway be defined, and have no default value
application.directory=APPLICATION_PATH

;following configs have default value, you may no need to define them
application.library = APPLICATION_PATH . "/library"
application.dispatcher.throwException=1
application.dispatcher.catchException=1

application.baseUri=""

;the php script ext name
ap.ext=php

;the view template ext name
ap.view.ext=phtml

ap.dispatcher.defaultModuel=Index
ap.dispatcher.defaultController=Index
ap.dispatcher.defaultAction=index

;defined modules
ap.modules=Index
```

`envrion`  
Which section will be loaded as the final config

### Return Values

### Examples

**Example \#2 <span
class="function">Yaf\_Application::\_\_construct</span>example**

``` php
<?php
defined('APPLICATION_PATH')                  // APPLICATION_PATH will be used in the ini config file
    || define('APPLICATION_PATH', __DIR__)); //__DIR__ was introduced after PHP 5.3

$application = new Yaf_Application(APPLICATION_PATH.'/conf/application.ini');
$application->bootstrap()->run();
?>
```

The above example will output something similar to:

**Example \#3 <span
class="function">Yaf\_Application::\_\_construct</span>example**

``` php
<?php
$config = array(
    "application" => array(
        "directory" => realpath(dirname(__FILE__)) . "/application",
    ),
);

/** Yaf_Application */
$application = new Yaf_Application($config);
$application->bootstrap()->run();
?>
```

The above example will output something similar to:

### See Also

-   <span class="classname">Yaf\_Config\_Ini</span>

Yaf\_Application::\_\_destruct
==============================

The \_\_destruct purpose

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Application::\_\_destruct</span> ( <span
class="methodparam">void</span> )

### Parameters

This function has no parameters.

### Return Values

Yaf\_Application::environ
=========================

Retrive environ

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Application::environ</span> ( <span
class="methodparam">void</span> )

Retrive environ which was defined in yaf.environ which has a default
value "product".

### Parameters

This function has no parameters.

### Return Values

### Examples

**Example \#1 <span
class="function">Yaf\_Application::environ</span>example**

``` php
<?php
$config = array(
    "application" => array(
        "directory" => realpath(dirname(__FILE__)) . "/application",
    ),
);

/** Yaf_Application */
$application = new Yaf_Application($config);
print_r($application->environ());
?>
```

The above example will output something similar to:

    product

Yaf\_Application::execute
=========================

Execute a callback

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Application::execute</span> ( <span
class="methodparam"><span class="type">callable</span> `$entry`</span> ,
<span class="methodparam"><span class="type">string</span> `$...`</span>
)

This method is typically used to run Yaf\_Application in a crontab work.
Make the crontab work can also use the autoloader and Bootstrap
mechanism.

### Parameters

`entry`  
a valid callback

`...`  
parameters will pass to the callback

### Return Values

### Examples

**Example \#1 <span
class="function">Yaf\_Application::execute</span>example**

``` php
<?php
function main($argc, $argv) {
}

$config = array(
    "application" => array(
        "directory" => realpath(dirname(__FILE__)) . "/application",
    ),
);

/** Yaf_Application */
$application = new Yaf_Application($config);
$application->execute("main", $argc,  $argv);
?>
```

The above example will output something similar to:

Yaf\_Application::getAppDirectory
=================================

Get the application directory

### Description

<span class="modifier">public</span> <span
class="type">Yaf\_Application</span> <span
class="methodname">Yaf\_Application::getAppDirectory</span> ( <span
class="methodparam">void</span> )

### Parameters

`directory`  

### Return Values

Yaf\_Application::getConfig
===========================

Retrive the config instance

### Description

<span class="modifier">public</span> <span
class="type">Yaf\_Config\_Abstract</span> <span
class="methodname">Yaf\_Application::getConfig</span> ( <span
class="methodparam">void</span> )

### Parameters

This function has no parameters.

### Return Values

A <span class="classname">Yaf\_Config\_Abstract</span> instance

### Examples

**Example \#1 <span
class="function">Yaf\_Application::getConfig</span>example**

``` php
<?php
$config = array(
    "application" => array(
        "directory" => realpath(dirname(__FILE__)) . "/application",
    ),
);

/** Yaf_Application */
$application = new Yaf_Application($config);
print_r($application->getConfig());
?>
```

The above example will output something similar to:

    Yaf_Config_Simple Object
    (
        [_config:protected] => Array
            (
                [application] => Array
                    (
                        [directory] => /home/laruence/local/www/htdocs/application
                    )

            )

        [_readonly:protected] => 1
    )

Yaf\_Application::getDispatcher
===============================

Get Yaf\_Dispatcher instance

### Description

<span class="modifier">public</span> <span
class="type">Yaf\_Dispatcher</span> <span
class="methodname">Yaf\_Application::getDispatcher</span> ( <span
class="methodparam">void</span> )

### Parameters

This function has no parameters.

### Return Values

### Examples

**Example \#1 <span
class="function">Yaf\_Application::getDispatcher</span>example**

``` php
<?php
$config = array(
    "application" => array(
        "directory" => realpath(dirname(__FILE__)) . "/application",
    ),
);

/** Yaf_Application */
$application = new Yaf_Application($config);
print_r($application->getDispatcher());
?>
```

The above example will output something similar to:

    Yaf_Dispatcher Object
    (
        [_router:protected] => Yaf_Router Object
            (
                [_routes:protected] => Array
                    (
                        [_default] => Yaf_Route_Static Object
                            (
                            )

                    )

                [_current:protected] => 
            )

        [_view:protected] => 
        [_request:protected] => Yaf_Request_Http Object
            (
                [module] => 
                [controller] => 
                [action] => 
                [method] => Cli
                [params:protected] => Array
                    (
                    )

                [language:protected] => 
                [_exception:protected] => 
                [_base_uri:protected] => 
                [uri:protected] => 
                [dispatched:protected] => 
                [routed:protected] => 
            )

        [_plugins:protected] => Array
            (
            )

        [_auto_render:protected] => 1
        [_return_response:protected] => 
        [_instantly_flush:protected] => 
        [_default_module:protected] => Index
        [_default_controller:protected] => Index
        [_default_action:protected] => index
        [_response] => Yaf_Response_Cli Object
            (
                [_header:protected] => Array
                    (
                    )

                [_body:protected] => 
                [_sendheader:protected] => 
            )

    )

Yaf\_Application::getLastErrorMsg
=================================

Get message of the last occurred error

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">Yaf\_Application::getLastErrorMsg</span> (
<span class="methodparam">void</span> )

### Parameters

This function has no parameters.

### Return Values

### Examples

**Example \#1 <span
class="function">Yaf\_Application::getLastErrorMsg</span>example**

``` php
<?php
function error_handler($errno, $errstr, $errfile, $errline) {
   var_dump(Yaf_Application::app()->getLastErrorMsg());
}

$config = array(                   
 "application" => array(
   "directory" => "/tmp/notexists",
     "dispatcher" => array(
       "throwException" => 0, //trigger error instead of throw exception when error occure
      ),
  ),
);

$app = new Yaf_Application($config);
$app->getDispatcher()->setErrorHandler("error_handler", E_RECOVERABLE_ERROR);
$app->run();
?>
```

The above example will output something similar to:

    string(69) "Could not find controller script /tmp/notexists/controllers/Index.php"

Yaf\_Application::getLastErrorNo
================================

Get code of last occurred error

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">Yaf\_Application::getLastErrorNo</span> ( <span
class="methodparam">void</span> )

### Parameters

This function has no parameters.

### Return Values

### Examples

**Example \#1 <span
class="function">Yaf\_Application::getLastErrorNo</span>example**

``` php
<?php
function error_handler($errno, $errstr, $errfile, $errline) {
   var_dump(Yaf_Application::app()->getLastErrorNo());
   var_dump(Yaf_Application::app()->getLastErrorNo() == YAF_ERR_NOTFOUND_CONTROLLER);
}

$config = array(
  "application" => array(
   "directory" => "/tmp/notexists",
     "dispatcher" => array(
       "throwException" => 0, //trigger error instead of throw exception when error occure
      ),
  ),
);

$app = new Yaf_Application($config);
$app->getDispatcher()->setErrorHandler("error_handler", E_RECOVERABLE_ERROR);
$app->run();
?>
```

The above example will output something similar to:

    int(516)
    bool(true)

Yaf\_Application::getModules
============================

Get defined module names

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">Yaf\_Application::getModules</span> ( <span
class="methodparam">void</span> )

Get the modules list defined in config, if no one defined, there will
always be a module named "Index".

### Parameters

This function has no parameters.

### Return Values

### Examples

**Example \#1 <span
class="function">Yaf\_Application::getModules</span>example**

``` php
<?php
$config = array(
    "application" => array(
        "directory" => realpath(dirname(__FILE__)) . "/application",
    ),
);

/** Yaf_Application */
$application = new Yaf_Application($config);
print_r($application->getModules());
?>
```

The above example will output something similar to:

    Array
    (
        [0] => Index
    )

Yaf\_Application::run
=====================

Start Yaf\_Application

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Application::run</span> ( <span
class="methodparam">void</span> )

Run a Yaf\_Application, let the Yaf\_Application accept a request and
route this request, dispatch to controller/action and render response.
Finally, return the response to the client.

### Parameters

This function has no parameters.

### Return Values

Yaf\_Application::setAppDirectory
=================================

Change the application directory

### Description

<span class="modifier">public</span> <span
class="type">Yaf\_Application</span> <span
class="methodname">Yaf\_Application::setAppDirectory</span> ( <span
class="methodparam"><span class="type">string</span> `$directory`</span>
)

### Parameters

`directory`  

### Return Values

Introduction
------------

Bootstrap is a mechanism used to do some initial config before a
Application run.

User may define their own Bootstrap class by inheriting <span
class="classname">Yaf\_Bootstrap\_Abstract</span>

Any method declared in Bootstrap class with leading "\_init", will be
called by <span class="methodname">Yaf\_Application::bootstrap</span>
one by one according to their defined order.

Examples
--------

**Example \#1 Bootstrap example**

``` php
<?php
   /* bootstrap class should be defined under ./application/Bootstrap.php */
   class Bootstrap extends Yaf_Bootstrap_Abstract {
        public function _initConfig(Yaf_Dispatcher $dispatcher) {
            var_dump(__METHOD__);
        }
        public function _initPlugin(Yaf_Dispatcher $dispatcher) {
            var_dump(__METHOD__);
        }
   }

   $config = array(
       "application" => array(
           "directory" => dirname(__FILE__) . "/application/",
       ),
   );
 
   $app = new Yaf_Application($config);
   $app->bootstrap();
?>
```

The above example will output something similar to:

    string(22) "Bootstrap::_initConfig"
    string(22) "Bootstrap::_initPlugin"

Class synopsis
--------------

**Yaf\_Bootstrap\_Abstract**

<span class="ooclass"> <span class="modifier">abstract</span> class
**Yaf\_Bootstrap\_Abstract** </span> {

/\* Properties \*/

/\* Methods \*/

}

Introduction
------------

<span class="classname">Yaf\_Dispatcher</span> purpose is to initialize
the request environment, route the incoming request, and then dispatch
any discovered actions; it aggregates any responses and returns them
when the process is complete.

<span class="classname">Yaf\_Dispatcher</span> also implements the
Singleton pattern, meaning only a single instance of it may be available
at any given time. This allows it to also act as a registry on which the
other objects in the dispatch process may draw.

Class synopsis
--------------

**Yaf\_Dispatcher**

<span class="ooclass"> <span class="modifier">final</span> class
**Yaf\_Dispatcher** </span> {

/\* Properties \*/

<span class="modifier">protected</span> `$_router` ;

<span class="modifier">protected</span> `$_view` ;

<span class="modifier">protected</span> `$_request` ;

<span class="modifier">protected</span> `$_plugins` ;

<span class="modifier">protected</span> <span
class="modifier">static</span> `$_instance` ;

<span class="modifier">protected</span> `$_auto_render` ;

<span class="modifier">protected</span> `$_return_response` ;

<span class="modifier">protected</span> `$_instantly_flush` ;

<span class="modifier">protected</span> `$_default_module` ;

<span class="modifier">protected</span> `$_default_controller` ;

<span class="modifier">protected</span> `$_default_action` ;

/\* Methods \*/

<span class="modifier">public</span> <span
class="type">Yaf\_Dispatcher</span> <span
class="methodname">autoRender</span> (\[ <span class="methodparam"><span
class="type">bool</span> `$flag`</span> \] )

<span class="modifier">public</span> <span
class="type">Yaf\_Dispatcher</span> <span
class="methodname">catchException</span> (\[ <span
class="methodparam"><span class="type">bool</span> `$flag`</span> \] )

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">disableView</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="type">Yaf\_Response\_Abstract</span> <span
class="methodname">dispatch</span> ( <span class="methodparam"><span
class="type">Yaf\_Request\_Abstract</span> `$request`</span> )

<span class="modifier">public</span> <span
class="type">Yaf\_Dispatcher</span> <span
class="methodname">enableView</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="type">Yaf\_Dispatcher</span> <span
class="methodname">flushInstantly</span> (\[ <span
class="methodparam"><span class="type">bool</span> `$flag`</span> \] )

<span class="modifier">public</span> <span
class="type">Yaf\_Application</span> <span
class="methodname">getApplication</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getDefaultAction</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getDefaultController</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getDefaultModule</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">Yaf\_Dispatcher</span>
<span class="methodname">getInstance</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="type">Yaf\_Request\_Abstract</span> <span
class="methodname">getRequest</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="type">Yaf\_Router</span> <span
class="methodname">getRouter</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="type">Yaf\_View\_Interface</span> <span
class="methodname">initView</span> ( <span class="methodparam"><span
class="type">string</span> `$templates_dir`</span> \[, <span
class="methodparam"><span class="type">array</span> `$options`</span> \]
)

<span class="modifier">public</span> <span
class="type">Yaf\_Dispatcher</span> <span
class="methodname">registerPlugin</span> ( <span
class="methodparam"><span class="type">Yaf\_Plugin\_Abstract</span>
`$plugin`</span> )

<span class="modifier">public</span> <span
class="type">Yaf\_Dispatcher</span> <span
class="methodname">returnResponse</span> ( <span
class="methodparam"><span class="type">bool</span> `$flag`</span> )

<span class="modifier">public</span> <span
class="type">Yaf\_Dispatcher</span> <span
class="methodname">setDefaultAction</span> ( <span
class="methodparam"><span class="type">string</span> `$action`</span> )

<span class="modifier">public</span> <span
class="type">Yaf\_Dispatcher</span> <span
class="methodname">setDefaultController</span> ( <span
class="methodparam"><span class="type">string</span>
`$controller`</span> )

<span class="modifier">public</span> <span
class="type">Yaf\_Dispatcher</span> <span
class="methodname">setDefaultModule</span> ( <span
class="methodparam"><span class="type">string</span> `$module`</span> )

<span class="modifier">public</span> <span
class="type">Yaf\_Dispatcher</span> <span
class="methodname">setErrorHandler</span> ( <span
class="methodparam"><span class="type">call</span> `$callback`</span> ,
<span class="methodparam"><span class="type">int</span>
`$error_types`</span> )

<span class="modifier">public</span> <span
class="type">Yaf\_Dispatcher</span> <span
class="methodname">setRequest</span> ( <span class="methodparam"><span
class="type">Yaf\_Request\_Abstract</span> `$request`</span> )

<span class="modifier">public</span> <span
class="type">Yaf\_Dispatcher</span> <span
class="methodname">setView</span> ( <span class="methodparam"><span
class="type">Yaf\_View\_Interface</span> `$view`</span> )

<span class="modifier">public</span> <span
class="type">Yaf\_Dispatcher</span> <span
class="methodname">throwException</span> (\[ <span
class="methodparam"><span class="type">bool</span> `$flag`</span> \] )

}

Properties
----------

`_router`  

`_view`  

`_request`  

`_plugins`  

`_instance`  

`_auto_render`  

`_return_response`  

`_instantly_flush`  

`_default_module`  

`_default_controller`  

`_default_action`  

Yaf\_Dispatcher::autoRender
===========================

Switch on/off autorendering

### Description

<span class="modifier">public</span> <span
class="type">Yaf\_Dispatcher</span> <span
class="methodname">Yaf\_Dispatcher::autoRender</span> (\[ <span
class="methodparam"><span class="type">bool</span> `$flag`</span> \] )

<span class="classname">Yaf\_Dispatcher</span> will render automatically
after dispatches a incoming request, you can prevent the rendering by
calling this method with `flag` **`TRUE`**

> **Note**:
>
> you can simply return **`FALSE`** in a action to prevent the
> auto-rendering of that action

### Parameters

`flag`  
bool

> **Note**:
>
> since 2.2.0, if this parameter is not given, then the current state
> will be renturned

### Return Values

### Examples

**Example \#1 <span
class="function">Yaf\_Dispatcher::autoRender</span>example**

``` php
<?php
class IndexController extends Yaf_Controller_Abstract {
     /* init method will be called as soon as a controller is initialized */ 
     public function init() {
         if ($this->getRequest()->isXmlHttpRequest()) {
             //do not call render for ajax request
             //we will outpu a json string
             Yaf_Dispatcher::getInstance()->autoRender(FALSE);
         }
     } 

}
?>
```

The above example will output something similar to:

Yaf\_Dispatcher::catchException
===============================

Switch on/off exception catching

### Description

<span class="modifier">public</span> <span
class="type">Yaf\_Dispatcher</span> <span
class="methodname">Yaf\_Dispatcher::catchException</span> (\[ <span
class="methodparam"><span class="type">bool</span> `$flag`</span> \] )

While the application.dispatcher.throwException is On(you can also
calling to <span
class="methodname">Yaf\_Dispatcher::throwException(TRUE)</span> to
enable it), Yaf will throw Exception whe error occurrs instead of
trigger error.

then if you enable <span
class="methodname">Yaf\_Dispatcher::catchException</span>(also can
enabled by set
<a href="/yaf/appconfig.html#" class="link">application.dispatcher.catchException</a>),
all uncaught Exceptions will be caught by ErrorController::error if you
have defined one.

### Parameters

`flag`  
bool

### Return Values

### Examples

**Example \#1 <span
class="function">Yaf\_Dispatcher::catchException</span>example**

``` php
/* if you defined a ErrorController like following */
<?php
class ErrorController extends Yaf_Controller_Abstract {
     /** 
      * you can also call to Yaf_Request_Abstract::getException to get the 
      * un-caught exception.
      */
     public function errorAction($exception) {
        /* error occurs */
        switch ($exception->getCode()) {
            case YAF_ERR_NOTFOUND_MODULE:
            case YAF_ERR_NOTFOUND_CONTROLLER:
            case YAF_ERR_NOTFOUND_ACTION:
            case YAF_ERR_NOTFOUND_VIEW:
                echo 404, ":", $exception->getMessage();
                break;
            default :
                $message = $exception->getMessage();
                echo 0, ":", $exception->getMessage();
                break;
        }
     } 
}
?>
```

The above example will output something similar to:

    /* now if some error occur, assuming access a non-exists controller(or you can throw a exception yourself): */
    404:Could not find controller script **/application/controllers/No-exists-controller.php

### See Also

-   <span class="methodname">Yaf\_Dispatcher::throwException</span>
-   <span class="methodname">Yaf\_Dispatcher::setErrorHandler</span>

Yaf\_Dispatcher::\_\_construct
==============================

Yaf\_Dispatcher constructor

### Description

<span class="modifier">public</span> <span
class="methodname">Yaf\_Dispatcher::\_\_construct</span> ( <span
class="methodparam">void</span> )

### Parameters

This function has no parameters.

### Return Values

Yaf\_Dispatcher::disableView
============================

Disable view rendering

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Yaf\_Dispatcher::disableView</span> ( <span
class="methodparam">void</span> )

disable view engine, used in some app that user will output by theirself

> **Note**:
>
> you can simply return **`FALSE`** in a action to prevent the
> auto-rendering of that action

### Parameters

This function has no parameters.

### Return Values

Yaf\_Dispatcher::dispatch
=========================

Dispatch a request

### Description

<span class="modifier">public</span> <span
class="type">Yaf\_Response\_Abstract</span> <span
class="methodname">Yaf\_Dispatcher::dispatch</span> ( <span
class="methodparam"><span class="type">Yaf\_Request\_Abstract</span>
`$request`</span> )

This method does the heavy work of the <span
class="classname">Yaf\_Dispatcher</span>. It take a request object.

The dispatch process has three distinct events:

-   Routing
-   Dispatching
-   Response

Routing takes place exactly once, using the values in the request object
when dispatch() is called. Dispatching takes place in a loop; a request
may either indicate multiple actions to dispatch, or the controller or a
plugin may reset the request object to force additional actions to
dispatch(see <span class="classname">Yaf\_Plugin\_Abstract</span>. When
all is done, the <span class="classname">Yaf\_Dispatcher</span> returns
a response.

### Parameters

`request`  

### Return Values

Yaf\_Dispatcher::enableView
===========================

Enable view rendering

### Description

<span class="modifier">public</span> <span
class="type">Yaf\_Dispatcher</span> <span
class="methodname">Yaf\_Dispatcher::enableView</span> ( <span
class="methodparam">void</span> )

### Parameters

This function has no parameters.

### Return Values

Yaf\_Dispatcher::flushInstantly
===============================

Switch on/off the instant flushing

### Description

<span class="modifier">public</span> <span
class="type">Yaf\_Dispatcher</span> <span
class="methodname">Yaf\_Dispatcher::flushInstantly</span> (\[ <span
class="methodparam"><span class="type">bool</span> `$flag`</span> \] )

### Parameters

`flag`  
bool

> **Note**:
>
> since 2.2.0, if this parameter is not given, then the current state
> will be renturned

### Return Values

Yaf\_Dispatcher::getApplication
===============================

Retrive the application

### Description

<span class="modifier">public</span> <span
class="type">Yaf\_Application</span> <span
class="methodname">Yaf\_Dispatcher::getApplication</span> ( <span
class="methodparam">void</span> )

Retrive the <span class="classname">Yaf\_Application</span> instance.
same as <span class="methodname">Yaf\_Application::app</span>.

### Parameters

This function has no parameters.

### Return Values

### See Also

-   <span class="methodname">Yaf\_Application::app</span>

Yaf\_Dispatcher::getDefaultAction
=================================

Retrive the default action name

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">Yaf\_Dispatcher::getDefaultAction</span> (
<span class="methodparam">void</span> )

get the default action name

### Parameters

This function has no parameters.

### Return Values

<span class="type">string</span>, default action name, default is
"index"

Yaf\_Dispatcher::getDefaultController
=====================================

Retrive the default controller name

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">Yaf\_Dispatcher::getDefaultController</span> (
<span class="methodparam">void</span> )

get the default controller name

### Parameters

This function has no parameters.

### Return Values

<span class="type">string</span>, default controller name, default is
"Index"

Yaf\_Dispatcher::getDefaultModule
=================================

Retrive the default module name

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">Yaf\_Dispatcher::getDefaultModule</span> (
<span class="methodparam">void</span> )

get the default module name

### Parameters

This function has no parameters.

### Return Values

<span class="type">string</span>, module name, default is "Index"

Yaf\_Dispatcher::getInstance
============================

Retrive the dispatcher instance

### Description

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">Yaf\_Dispatcher</span>
<span class="methodname">Yaf\_Dispatcher::getInstance</span> ( <span
class="methodparam">void</span> )

### Parameters

This function has no parameters.

### Return Values

Yaf\_Dispatcher::getRequest
===========================

Retrive the request instance

### Description

<span class="modifier">public</span> <span
class="type">Yaf\_Request\_Abstract</span> <span
class="methodname">Yaf\_Dispatcher::getRequest</span> ( <span
class="methodparam">void</span> )

### Parameters

This function has no parameters.

### Return Values

Yaf\_Dispatcher::getRouter
==========================

Retrive router instance

### Description

<span class="modifier">public</span> <span
class="type">Yaf\_Router</span> <span
class="methodname">Yaf\_Dispatcher::getRouter</span> ( <span
class="methodparam">void</span> )

### Parameters

This function has no parameters.

### Return Values

Yaf\_Dispatcher::initView
=========================

Initialize view and return it

### Description

<span class="modifier">public</span> <span
class="type">Yaf\_View\_Interface</span> <span
class="methodname">Yaf\_Dispatcher::initView</span> ( <span
class="methodparam"><span class="type">string</span>
`$templates_dir`</span> \[, <span class="methodparam"><span
class="type">array</span> `$options`</span> \] )

### Parameters

`templates_dir`  

`options`  

### Return Values

Yaf\_Dispatcher::registerPlugin
===============================

Register a plugin

### Description

<span class="modifier">public</span> <span
class="type">Yaf\_Dispatcher</span> <span
class="methodname">Yaf\_Dispatcher::registerPlugin</span> ( <span
class="methodparam"><span class="type">Yaf\_Plugin\_Abstract</span>
`$plugin`</span> )

Register a plugin(see <span
class="classname">Yaf\_Plugin\_Abstract</span>). Generally, we register
plugins in Bootstrap(see <span
class="classname">Yaf\_Bootstrap\_Abstract</span>).

### Parameters

`plugin`  

### Return Values

### Examples

**Example \#1 <span
class="function">Yaf\_Dispatcher::registerPlugin</span>example**

``` php
<?php
class Bootstrap extends Yaf_Bootstrap_Abstract {
  public function _initPlugin(Yaf_Dispatcher $dispatcher) {
    /**
    * Yaf assumes plugin scripts under [application.directory] .  "/plugins" 
    * for this case, it will be:
    * [application.directory] . "/plugins/" . "User" . [application.ext]
    */ 
    $user = new UserPlugin();
    $dispatcher->registerPlugin($user);
  }
}
?>
```

### See Also

-   <span class="classname">Yaf\_Plugin\_Abstract</span>

<!-- -->

-   <span class="classname">Yaf\_Bootstrap\_Abstract</span>

Yaf\_Dispatcher::returnResponse
===============================

The returnResponse purpose

### Description

<span class="modifier">public</span> <span
class="type">Yaf\_Dispatcher</span> <span
class="methodname">Yaf\_Dispatcher::returnResponse</span> ( <span
class="methodparam"><span class="type">bool</span> `$flag`</span> )

### Parameters

`flag`  

### Return Values

Yaf\_Dispatcher::setDefaultAction
=================================

Change default action name

### Description

<span class="modifier">public</span> <span
class="type">Yaf\_Dispatcher</span> <span
class="methodname">Yaf\_Dispatcher::setDefaultAction</span> ( <span
class="methodparam"><span class="type">string</span> `$action`</span> )

### Parameters

`action`  

### Return Values

Yaf\_Dispatcher::setDefaultController
=====================================

Change default controller name

### Description

<span class="modifier">public</span> <span
class="type">Yaf\_Dispatcher</span> <span
class="methodname">Yaf\_Dispatcher::setDefaultController</span> ( <span
class="methodparam"><span class="type">string</span>
`$controller`</span> )

### Parameters

`controller`  

### Return Values

Yaf\_Dispatcher::setDefaultModule
=================================

Change default module name

### Description

<span class="modifier">public</span> <span
class="type">Yaf\_Dispatcher</span> <span
class="methodname">Yaf\_Dispatcher::setDefaultModule</span> ( <span
class="methodparam"><span class="type">string</span> `$module`</span> )

### Parameters

`module`  

### Return Values

Yaf\_Dispatcher::setErrorHandler
================================

Set error handler

### Description

<span class="modifier">public</span> <span
class="type">Yaf\_Dispatcher</span> <span
class="methodname">Yaf\_Dispatcher::setErrorHandler</span> ( <span
class="methodparam"><span class="type">call</span> `$callback`</span> ,
<span class="methodparam"><span class="type">int</span>
`$error_types`</span> )

Set error handler for Yaf. when
<a href="/yaf/appconfig.html#" class="link">application.dispatcher.throwException</a>
is off, Yaf will trigger catchable error while unexpected errors
occrred.

Thus, this error handler will be called while the error raise.

### Parameters

`callback`  
A callable callback

`error_types`  

### Return Values

### See Also

-   <span class="methodname">Yaf\_Dispatcher::throwException</span>
-   <span class="methodname">Yaf\_Application::getLastErrorNo</span>
-   <span class="methodname">Yaf\_Application::getLastErrorMsg</span>

Yaf\_Dispatcher::setRequest
===========================

The setRequest purpose

### Description

<span class="modifier">public</span> <span
class="type">Yaf\_Dispatcher</span> <span
class="methodname">Yaf\_Dispatcher::setRequest</span> ( <span
class="methodparam"><span class="type">Yaf\_Request\_Abstract</span>
`$request`</span> )

### Parameters

`plugin`  

### Return Values

Yaf\_Dispatcher::setView
========================

Set a custom view engine

### Description

<span class="modifier">public</span> <span
class="type">Yaf\_Dispatcher</span> <span
class="methodname">Yaf\_Dispatcher::setView</span> ( <span
class="methodparam"><span class="type">Yaf\_View\_Interface</span>
`$view`</span> )

This method proviods a solution for that if you want use a custom view
engine instead of <span class="classname">Yaf\_View\_Simple</span>

### Parameters

`view`  
A Yaf\_View\_Interface instance

### Return Values

### Examples

**Example \#1 <span class="function">A custom View
engine</span>example**

``` php
<?php
require "/path/to/smarty/Smarty.class.php";

class Smarty_Adapter implements Yaf_View_Interface
{
    /**
     * Smarty object
     * @var Smarty
     */
    public $_smarty;
 
    /**
     * Constructor
     *
     * @param string $tmplPath
     * @param array $extraParams
     * @return void
     */
    public function __construct($tmplPath = null, $extraParams = array()) {
        $this->_smarty = new Smarty;
 
        if (null !== $tmplPath) {
            $this->setScriptPath($tmplPath);
        }
 
        foreach ($extraParams as $key => $value) {
            $this->_smarty->$key = $value;
        }
    }
 
    /**
     * Set the path to the templates
     *
     * @param string $path The directory to set as the path.
     * @return void
     */
    public function setScriptPath($path)
    {
        if (is_readable($path)) {
            $this->_smarty->template_dir = $path;
            return;
        }
 
        throw new Exception('Invalid path provided');
    }
 
    /**
     * Assign a variable to the template
     *
     * @param string $key The variable name.
     * @param mixed $val The variable value.
     * @return void
     */
    public function __set($key, $val)
    {
        $this->_smarty->assign($key, $val);
    }
 
    /**
     * Allows testing with empty() and isset() to work
     *
     * @param string $key
     * @return boolean
     */
    public function __isset($key)
    {
        return (null !== $this->_smarty->get_template_vars($key));
    }
 
    /**
     * Allows unset() on object properties to work
     *
     * @param string $key
     * @return void
     */
    public function __unset($key)
    {
        $this->_smarty->clear_assign($key);
    }
 
    /**
     * Assign variables to the template
     *
     * Allows setting a specific key to the specified value, OR passing
     * an array of key => value pairs to set en masse.
     *
     * @see __set()
     * @param string|array $spec The assignment strategy to use (key or
     * array of key => value pairs)
     * @param mixed $value (Optional) If assigning a named variable,
     * use this as the value.
     * @return void
     */
    public function assign($spec, $value = null) {
        if (is_array($spec)) {
            $this->_smarty->assign($spec);
            return;
        }
 
        $this->_smarty->assign($spec, $value);
    }
 
    /**
     * Clear all assigned variables
     *
     * Clears all variables assigned to Yaf_View either via
     * {@link assign()} or property overloading
     * ({@link __get()}/{@link __set()}).
     *
     * @return void
     */
    public function clearVars() {
        $this->_smarty->clear_all_assign();
    }
 
    /**
     * Processes a template and returns the output.
     *
     * @param string $name The template to process.
     * @return string The output.
     */
    public function render($name, $value = NULL) {
        return $this->_smarty->fetch($name);
    }

    public function display($name, $value = NULL) {
        echo $this->_smarty->fetch($name);
    }

}
?>
```

**Example \#2 <span
class="function">Yaf\_Dispatcher::setView</span>example**

``` php
<?php
class Bootstrap extends Yaf_Bootstrap_Abstract {

    /**
     * there are some config for smarty in the config:
     *
     * smarty.left_delimiter   = "{{"
     * smarty.right_delimiter  = "}}"
     * smarty.template_dir     = APPLICATION_PATH "/views/scripts/"
     * smarty.compile_dir      = APPLICATION_PATH "/views/templates_c/"
     * smarty.cache_dir        = APPLICATION_PATH "/views/templates_d/"
     *
     */
    public function _initConfig() {
        $config = Yaf_Application::app()->getConfig();
        Yaf_Registry::set("config", $config);
    }

    public function _initLocalName() {
        /** we put class Smarty_Adapter under the local library directory */
        Yaf_Loader::getInstance()->registerLocalNamespace('Smarty');
    }

    public function _initSmarty(Yaf_Dispatcher $dispatcher) {
        $smarty = new Smarty_Adapter(null, Yaf_Registry::get("config")->get("smarty"));
        $dispatcher->setView($smarty);
        /* now the Smarty view engine become the default view engine of Yaf */
    }
}
?>
```

### See Also

-   <span class="classname">Yaf\_View\_Interface</span>
-   <span class="classname">Yaf\_View\_Simple</span>

Yaf\_Dispatcher::throwException
===============================

Switch on/off exception throwing

### Description

<span class="modifier">public</span> <span
class="type">Yaf\_Dispatcher</span> <span
class="methodname">Yaf\_Dispatcher::throwException</span> (\[ <span
class="methodparam"><span class="type">bool</span> `$flag`</span> \] )

Siwtch on/off exception throwing while unexpected error occurring. When
this is on, Yaf will throwing exceptions instead of triggering catchable
errors.

You can also use
<a href="/yaf/appconfig.html#" class="link">application.dispatcher.throwException</a>
to achieve the same purpose.

### Parameters

`flag`  
bool

### Return Values

### Examples

**Example \#1 <span
class="function">Yaf\_Dispatcher::throwexception</span>example**

``` php
<?php

$config = array(
    'application' => array(
        'directory' => dirname(__FILE__),
    ),
);
$app = new Yaf_Application($config);

$app->getDispatcher()->throwException(true);

try {
    $app->run();
} catch (Yaf_Exception $e) {
    var_dump($e->getMessage());
}
?>
```

The above example will output something similar to:

    string(59) "Could not find controller script /tmp/controllers/Index.php"

**Example \#2 <span
class="function">Yaf\_Dispatcher::throwexception</span>example**

``` php
<?php

$config = array(
    'application' => array(
        'directory' => dirname(__FILE__),
    ),
);
$app = new Yaf_Application($config);

$app->getDispatcher()->throwException(false);

$app->run();
?>
```

The above example will output something similar to:

    PHP Catchable fatal error:  Yaf_Application::run(): Could not find controller script /tmp/controllers/Index.php in /tmp/1.php on line 12

### See Also

-   <span class="methodname">Yaf\_Dispatcher::catchException</span>
-   <span class="classname">Yaf\_Exception</span>

Introduction
------------

Class synopsis
--------------

**Yaf\_Config\_Abstract**

<span class="ooclass"> <span class="modifier">abstract</span> class
**Yaf\_Config\_Abstract** </span> {

/\* Properties \*/

<span class="modifier">protected</span> `$_config` ;

<span class="modifier">protected</span> `$_readonly` ;

/\* Methods \*/

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type">mixed</span> <span
class="methodname">get</span> ( <span class="methodparam"><span
class="type">string</span> `$name`</span> , <span
class="methodparam"><span class="type">mixed</span> `$value`</span> )

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type">bool</span> <span
class="methodname">readonly</span> ( <span
class="methodparam">void</span> )

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span
class="type">Yaf\_Config\_Abstract</span> <span
class="methodname">set</span> ( <span class="methodparam">void</span> )

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type">array</span> <span
class="methodname">toArray</span> ( <span
class="methodparam">void</span> )

}

Properties
----------

`_config`  

`_readonly`  

Yaf\_Config\_Abstract::get
==========================

Getter

### Description

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type">mixed</span> <span
class="methodname">Yaf\_Config\_Abstract::get</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> ,
<span class="methodparam"><span class="type">mixed</span>
`$value`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

Yaf\_Config\_Abstract::readonly
===============================

Find a config whether readonly

### Description

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type">bool</span> <span
class="methodname">Yaf\_Config\_Abstract::readonly</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

Yaf\_Config\_Abstract::set
==========================

Setter

### Description

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span
class="type">Yaf\_Config\_Abstract</span> <span
class="methodname">Yaf\_Config\_Abstract::set</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

Yaf\_Config\_Abstract::toArray
==============================

Cast to array

### Description

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type">array</span> <span
class="methodname">Yaf\_Config\_Abstract::toArray</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

Introduction
------------

Yaf\_Config\_Ini enables developers to store configuration data in a
familiar INI format and read them in the application by using nested
object property syntax. The INI format is specialized to provide both
the ability to have a hierarchy of configuration data keys and
inheritance between configuration data sections. Configuration data
hierarchies are supported by separating the keys with the dot or period
character ("."). A section may extend or inherit from another section by
following the section name with a colon character (":") and the name of
the section from which data are to be inherited.

> **Note**:
>
> Yaf\_Config\_Ini utilizes the » parse\_ini\_file() PHP function.
> Please review this documentation to be aware of its specific
> behaviors, which propagate to Yaf\_Config\_Ini, such as how the
> special values of "**`TRUE`**", "**`FALSE`**", "yes", "no", and
> "**`NULL`**" are handled.

Class synopsis
--------------

**Yaf\_Config\_Ini**

<span class="ooclass"> class **Yaf\_Config\_Ini** </span> <span
class="ooclass"> <span class="modifier">extends</span>
**Yaf\_Config\_Abstract** </span> <span class="oointerface">implements
<span class="interfacename">Iterator</span> </span> <span
class="oointerface">, <span class="interfacename">ArrayAccess</span>
</span> <span class="oointerface">, <span
class="interfacename">Countable</span> </span> {

/\* Properties \*/

/\* Methods \*/

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> ( <span
class="methodparam"><span class="type">string</span>
`$config_file`</span> \[, <span class="methodparam"><span
class="type">string</span> `$section`</span> \] )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">count</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">current</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">\_\_get</span> (\[ <span
class="methodparam"><span class="type">string</span> `$name`</span> \] )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">\_\_isset</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">key</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">next</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">offsetExists</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">offsetGet</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">offsetSet</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> ,
<span class="methodparam"><span class="type">string</span>
`$value`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">offsetUnset</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">readonly</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">rewind</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">\_\_set</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> ,
<span class="methodparam"><span class="type">mixed</span>
`$value`</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">toArray</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">valid</span> ( <span
class="methodparam">void</span> )

/\* Inherited methods \*/

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type">mixed</span> <span
class="methodname">Yaf\_Config\_Abstract::get</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> ,
<span class="methodparam"><span class="type">mixed</span>
`$value`</span> )

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type">bool</span> <span
class="methodname">Yaf\_Config\_Abstract::readonly</span> ( <span
class="methodparam">void</span> )

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span
class="type">Yaf\_Config\_Abstract</span> <span
class="methodname">Yaf\_Config\_Abstract::set</span> ( <span
class="methodparam">void</span> )

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type">array</span> <span
class="methodname">Yaf\_Config\_Abstract::toArray</span> ( <span
class="methodparam">void</span> )

}

Properties
----------

`_config`  

`_readonly`  

Examples
--------

**Example \#1 <span class="function">Yaf\_Config\_Ini</span>example**

This example illustrates a basic use of Yaf\_Config\_Ini for loading
configuration data from an INI file. In this example there are
configuration data for both a production system and for a staging
system. Because the staging system configuration data are very similar
to those for production, the staging section inherits from the
production section. In this case, the decision is arbitrary and could
have been written conversely, with the production section inheriting
from the staging section, though this may not be the case for more
complex situations. Suppose, then, that the following configuration data
are contained in /path/to/config.ini:

``` ini
; Production site configuration data
[production]
webhost                  = www.example.com
database.adapter         = pdo_mysql
database.params.host     = db.example.com
database.params.username = dbuser
database.params.password = secret
database.params.dbname   = dbname
 
; Staging site configuration data inherits from production and
; overrides values as necessary
[staging : production]
database.params.host     = dev.example.com
database.params.username = devuser
database.params.password = devsecret
```

``` php
<?php
$config = new Yaf_Config_Ini('/path/to/config.ini', 'staging');
 
var_dump($config->database->params->host); 
var_dump($config->database->params->dbname);
var_dump($config->get("database.params.username"));
?>
```

The above example will output something similar to:

    string(15) "dev.example.com"
    string(6) "dbname"
    string(7) "devuser

Yaf\_Config\_Ini::\_\_construct
===============================

Yaf\_Config\_Ini constructor

### Description

<span class="modifier">public</span> <span
class="methodname">Yaf\_Config\_Ini::\_\_construct</span> ( <span
class="methodparam"><span class="type">string</span>
`$config_file`</span> \[, <span class="methodparam"><span
class="type">string</span> `$section`</span> \] )

<span class="classname">Yaf\_Config\_Ini</span> constructor

### Parameters

`config_file`  
path to an INI configure file

`section`  
which section in that INI file you want to be parsed

### Return Values

Yaf\_Config\_Ini::count
=======================

Count all elements in Yaf\_Config.ini

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Config\_Ini::count</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

Yaf\_Config\_Ini::current
=========================

Retrieve the current value

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Config\_Ini::current</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

Yaf\_Config\_Ini::\_\_get
=========================

Retrieve a element

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Config\_Ini::\_\_get</span> (\[ <span
class="methodparam"><span class="type">string</span> `$name`</span> \] )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`name`  

### Return Values

Yaf\_Config\_Ini::\_\_isset
===========================

Determine if a key is exists

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Config\_Ini::\_\_isset</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`name`  

### Return Values

Yaf\_Config\_Ini::key
=====================

Fetch current element's key

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Config\_Ini::key</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

Yaf\_Config\_Ini::next
======================

Advance the internal pointer

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Config\_Ini::next</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

Yaf\_Config\_Ini::offsetExists
==============================

The offsetExists purpose

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Config\_Ini::offsetExists</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`name`  

### Return Values

Yaf\_Config\_Ini::offsetGet
===========================

The offsetGet purpose

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Config\_Ini::offsetGet</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`name`  

### Return Values

Yaf\_Config\_Ini::offsetSet
===========================

The offsetSet purpose

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Config\_Ini::offsetSet</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> ,
<span class="methodparam"><span class="type">string</span>
`$value`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`name`  

`value`  

### Return Values

Yaf\_Config\_Ini::offsetUnset
=============================

The offsetUnset purpose

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Config\_Ini::offsetUnset</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`name`  

### Return Values

Yaf\_Config\_Ini::readonly
==========================

The readonly purpose

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Config\_Ini::readonly</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

Yaf\_Config\_Ini::rewind
========================

The rewind purpose

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Config\_Ini::rewind</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

Yaf\_Config\_Ini::\_\_set
=========================

The \_\_set purpose

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Config\_Ini::\_\_set</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> ,
<span class="methodparam"><span class="type">mixed</span>
`$value`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`name`  

`value`  

### Return Values

Yaf\_Config\_Ini::toArray
=========================

Return config as a PHP array

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">Yaf\_Config\_Ini::toArray</span> ( <span
class="methodparam">void</span> )

Returns a PHP array from the <span
class="classname">Yaf\_Config\_Ini</span>

### Parameters

This function has no parameters.

### Return Values

Yaf\_Config\_Ini::valid
=======================

The valid purpose

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Config\_Ini::valid</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

Introduction
------------

Class synopsis
--------------

**Yaf\_Config\_Simple**

<span class="ooclass"> class **Yaf\_Config\_Simple** </span> <span
class="ooclass"> <span class="modifier">extends</span>
**Yaf\_Config\_Abstract** </span> <span class="oointerface">implements
<span class="interfacename">Iterator</span> </span> <span
class="oointerface">, <span class="interfacename">ArrayAccess</span>
</span> <span class="oointerface">, <span
class="interfacename">Countable</span> </span> {

/\* Properties \*/

<span class="modifier">protected</span> `$_readonly` ;

/\* Methods \*/

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> ( <span
class="methodparam"><span class="type">array</span> `$configs`</span>
\[, <span class="methodparam"><span class="type">bool</span>
`$readonly`<span class="initializer"> = false</span></span> \] )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">count</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">current</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">\_\_get</span> (\[ <span
class="methodparam"><span class="type">string</span> `$name`</span> \] )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">\_\_isset</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">key</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">next</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">offsetExists</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">offsetGet</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">offsetSet</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> ,
<span class="methodparam"><span class="type">string</span>
`$value`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">offsetUnset</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">readonly</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">rewind</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">\_\_set</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> ,
<span class="methodparam"><span class="type">string</span>
`$value`</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">toArray</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">valid</span> ( <span
class="methodparam">void</span> )

/\* Inherited methods \*/

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type">mixed</span> <span
class="methodname">Yaf\_Config\_Abstract::get</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> ,
<span class="methodparam"><span class="type">mixed</span>
`$value`</span> )

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type">bool</span> <span
class="methodname">Yaf\_Config\_Abstract::readonly</span> ( <span
class="methodparam">void</span> )

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span
class="type">Yaf\_Config\_Abstract</span> <span
class="methodname">Yaf\_Config\_Abstract::set</span> ( <span
class="methodparam">void</span> )

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type">array</span> <span
class="methodname">Yaf\_Config\_Abstract::toArray</span> ( <span
class="methodparam">void</span> )

}

Properties
----------

`_config`  

`_readonly`  

Yaf\_Config\_Simple::\_\_construct
==================================

The \_\_construct purpose

### Description

<span class="modifier">public</span> <span
class="methodname">Yaf\_Config\_Simple::\_\_construct</span> ( <span
class="methodparam"><span class="type">array</span> `$configs`</span>
\[, <span class="methodparam"><span class="type">bool</span>
`$readonly`<span class="initializer"> = false</span></span> \] )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`configs`  

`readonly`  

### Return Values

Yaf\_Config\_Simple::count
==========================

The count purpose

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Config\_Simple::count</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

Yaf\_Config\_Simple::current
============================

The current purpose

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Config\_Simple::current</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

Yaf\_Config\_Simple::\_\_get
============================

The \_\_get purpose

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Config\_Simple::\_\_get</span> (\[ <span
class="methodparam"><span class="type">string</span> `$name`</span> \] )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`name`  

### Return Values

Yaf\_Config\_Simple::\_\_isset
==============================

The \_\_isset purpose

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Config\_Simple::\_\_isset</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`name`  

### Return Values

Yaf\_Config\_Simple::key
========================

The key purpose

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Config\_Simple::key</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

Yaf\_Config\_Simple::next
=========================

The next purpose

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Config\_Simple::next</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

Yaf\_Config\_Simple::offsetExists
=================================

The offsetExists purpose

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Config\_Simple::offsetExists</span> (
<span class="methodparam"><span class="type">string</span>
`$name`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`name`  

### Return Values

Yaf\_Config\_Simple::offsetGet
==============================

The offsetGet purpose

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Config\_Simple::offsetGet</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`name`  

### Return Values

Yaf\_Config\_Simple::offsetSet
==============================

The offsetSet purpose

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Config\_Simple::offsetSet</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> ,
<span class="methodparam"><span class="type">string</span>
`$value`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`name`  

`value`  

### Return Values

Yaf\_Config\_Simple::offsetUnset
================================

The offsetUnset purpose

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Config\_Simple::offsetUnset</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`name`  

### Return Values

Yaf\_Config\_Simple::readonly
=============================

The readonly purpose

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Config\_Simple::readonly</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

Yaf\_Config\_Simple::rewind
===========================

The rewind purpose

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Config\_Simple::rewind</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

Yaf\_Config\_Simple::\_\_set
============================

The \_\_set purpose

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Config\_Simple::\_\_set</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> ,
<span class="methodparam"><span class="type">string</span>
`$value`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`name`  

`value`  

### Return Values

Yaf\_Config\_Simple::toArray
============================

Returns a PHP array

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">Yaf\_Config\_Simple::toArray</span> ( <span
class="methodparam">void</span> )

Returns a PHP array from the <span
class="classname">Yaf\_Config\_Simple</span>

### Parameters

This function has no parameters.

### Return Values

Yaf\_Config\_Simple::valid
==========================

The valid purpose

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Config\_Simple::valid</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

Introduction
------------

<span class="classname">Yaf\_Controller\_Abstract</span> is the heart of
Yaf's system. MVC stands for Model-View-Controller and is a design
pattern targeted at separating application logic from display logic.

Every custom controller shall inherit <span
class="classname">Yaf\_Controller\_Abstract</span>.

You will find that you can not define \_\_construct function for your
custom controller, thus, <span
class="classname">Yaf\_Controller\_Abstract</span> provides a magic
method: <span class="methodname">Yaf\_Controller\_Abstract::init</span>.

If you have defined a init() method in your custom controller, it will
be called as long as the controller was instantiated.

Action may have arguments, when a request coming, if there are the same
name variable in the request parameters(see <span
class="methodname">Yaf\_Request\_Abstract::getParam</span>) after
routed, Yaf will pass them to the action method (see <span
class="methodname">Yaf\_Action\_Abstract::execute</span>).

> **Note**:
>
> These arguments are directly fetched without filtering, it should be
> carefully processed before use them.

Class synopsis
--------------

**Yaf\_Controller\_Abstract**

<span class="ooclass"> <span class="modifier">abstract</span> class
**Yaf\_Controller\_Abstract** </span> {

/\* Properties \*/

<span class="modifier">public</span> `$actions` ;

<span class="modifier">protected</span> `$_module` ;

<span class="modifier">protected</span> `$_name` ;

<span class="modifier">protected</span> `$_request` ;

<span class="modifier">protected</span> `$_response` ;

<span class="modifier">protected</span> `$_invoke_args` ;

<span class="modifier">protected</span> `$_view` ;

/\* Methods \*/

<span class="modifier">final</span> <span
class="modifier">private</span> <span
class="methodname">\_\_construct</span> ( <span
class="methodparam">void</span> )

<span class="modifier">protected</span> <span class="type">bool</span>
<span class="methodname">display</span> ( <span
class="methodparam"><span class="type">string</span> `$tpl`</span> \[,
<span class="methodparam"><span class="type">array</span>
`$parameters`</span> \] )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">forward</span> ( <span
class="methodparam"><span class="type">string</span> `$action`</span>
\[, <span class="methodparam"><span class="type">array</span>
`$paramters`</span> \] )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">getInvokeArg</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">getInvokeArgs</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getModuleName</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getName</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="type">Yaf\_Request\_Abstract</span> <span
class="methodname">getRequest</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="type">Yaf\_Response\_Abstract</span> <span
class="methodname">getResponse</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="type">Yaf\_View\_Interface</span> <span
class="methodname">getView</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getViewpath</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">init</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">initView</span> (\[ <span
class="methodparam"><span class="type">array</span> `$options`</span> \]
)

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">redirect</span> ( <span
class="methodparam"><span class="type">string</span> `$url`</span> )

<span class="modifier">protected</span> <span class="type">string</span>
<span class="methodname">render</span> ( <span class="methodparam"><span
class="type">string</span> `$tpl`</span> \[, <span
class="methodparam"><span class="type">array</span> `$parameters`</span>
\] )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">setViewpath</span> ( <span
class="methodparam"><span class="type">string</span>
`$view_directory`</span> )

}

Properties
----------

`actions`  
You can also define a action method in a separate PHP script by using
this property and <span class="classname">Yaf\_Action\_Abstract</span>.

**Example \#1 define action in a separate file**

``` php
<?php
class IndexController extends Yaf_Controller_Abstract {
    protected $actions = array(
        /** now dummyAction is defined in a separate file */
        "dummy" => "actions/Dummy_action.php",
    );

    /* action method may have arguments */
    public indexAction($name, $id) {
       /* $name and $id are unsafe raw data */
       assert($name == $this->getRequest()->getParam("name"));
       assert($id   == $this->_request->getParam("id"));
    }
}
?>
```

**Example \#2 Dummy\_action.php**

``` php
<?php
class DummyAction extends Yaf_Action_Abstract {
    /* a action class shall define this method  as the entry point */
    public execute() {
    }
}
?>
```

`_module`  
module name

`_name`  
controller name

`_request`  
current request object

`_response`  
current response object

`_invoke_args`  

`_view`  
view engine object

Yaf\_Controller\_Abstract::\_\_construct
========================================

Yaf\_Controller\_Abstract constructor

### Description

<span class="modifier">final</span> <span
class="modifier">private</span> <span
class="methodname">Yaf\_Controller\_Abstract::\_\_construct</span> (
<span class="methodparam">void</span> )

<span class="methodname">Yaf\_Controller\_Abstract::\_\_construct</span>
is final, which means it can not be overridden. You may want to see
<span class="methodname">Yaf\_Controller\_Abstract::init</span> instead.

### Parameters

This function has no parameters.

### Return Values

### See Also

-   <span class="methodname">Yaf\_Controller\_Abstract::init</span>

Yaf\_Controller\_Abstract::display
==================================

The display purpose

### Description

<span class="modifier">protected</span> <span class="type">bool</span>
<span class="methodname">Yaf\_Controller\_Abstract::display</span> (
<span class="methodparam"><span class="type">string</span> `$tpl`</span>
\[, <span class="methodparam"><span class="type">array</span>
`$parameters`</span> \] )

### Parameters

`tpl`  

`parameters`  

### Return Values

Yaf\_Controller\_Abstract::forward
==================================

Foward to another action

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Controller\_Abstract::forward</span> (
<span class="methodparam"><span class="type">string</span>
`$action`</span> \[, <span class="methodparam"><span
class="type">array</span> `$paramters`</span> \] )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Controller\_Abstract::forward</span> (
<span class="methodparam"><span class="type">string</span>
`$controller`</span> , <span class="methodparam"><span
class="type">string</span> `$action`</span> \[, <span
class="methodparam"><span class="type">array</span> `$paramters`</span>
\] )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Controller\_Abstract::forward</span> (
<span class="methodparam"><span class="type">string</span>
`$module`</span> , <span class="methodparam"><span
class="type">string</span> `$controller`</span> , <span
class="methodparam"><span class="type">string</span> `$action`</span>
\[, <span class="methodparam"><span class="type">array</span>
`$paramters`</span> \] )

forward current execution process to other action.

> **Note**:
>
> this method doesn't switch to the destination action immediately, it
> will take place after current flow finish.

### Parameters

`module`  
destination module name, if NULL was given, then default module name is
assumed

`controller`  
destination controller name

`action`  
destination action name

`paramters`  
calling arguments

### Examples

**Example \#1 <span
class="function">Yaf\_Controller\_Abstract::forward</span>example**

``` php
<?php
class IndexController extends Yaf_Controller_Abstract
{
    public function indexAction(){   
         $logined = $_SESSION["login"];
         if (!$logined) {
             $this->forward("login", array("from" => "Index")); // forward to login action
             return FALSE;  // this is important, this finish current working flow
                            // and tell the Yaf do not doing auto-render
         }

         // other processes
    }

    public function loginAction() {
         echo "login, redirected from ", $this->_request->getParam("from") , " action";
    }
}
?>
```

The above example will output something similar to:

       login, redirected from Index action

### Return Values

return FALSE on failure

### See Also

-   <span class="methodname">Yaf\_Request\_Abstrace::getParam</span>

Yaf\_Controller\_Abstract::getInvokeArg
=======================================

The getInvokeArg purpose

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Controller\_Abstract::getInvokeArg</span>
( <span class="methodparam"><span class="type">string</span>
`$name`</span> )

### Parameters

`name`  

### Return Values

Yaf\_Controller\_Abstract::getInvokeArgs
========================================

The getInvokeArgs purpose

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Controller\_Abstract::getInvokeArgs</span>
( <span class="methodparam">void</span> )

### Parameters

This function has no parameters.

### Return Values

Yaf\_Controller\_Abstract::getModuleName
========================================

Get module name

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">Yaf\_Controller\_Abstract::getModuleName</span>
( <span class="methodparam">void</span> )

get the controller's module name

### Parameters

This function has no parameters.

### Return Values

Yaf\_Controller\_Abstract::getName
==================================

Get self name

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">Yaf\_Controller\_Abstract::getName</span> (
<span class="methodparam">void</span> )

get the controller's name

### Parameters

This function has no parameters.

### Return Values

<span class="type">string</span>, controller name

Yaf\_Controller\_Abstract::getRequest
=====================================

Retrieve current request object

### Description

<span class="modifier">public</span> <span
class="type">Yaf\_Request\_Abstract</span> <span
class="methodname">Yaf\_Controller\_Abstract::getRequest</span> ( <span
class="methodparam">void</span> )

retrieve current request object

### Parameters

This function has no parameters.

### Return Values

<span class="classname">Yaf\_Request\_Abstract</span> instance

Yaf\_Controller\_Abstract::getResponse
======================================

Retrieve current response object

### Description

<span class="modifier">public</span> <span
class="type">Yaf\_Response\_Abstract</span> <span
class="methodname">Yaf\_Controller\_Abstract::getResponse</span> ( <span
class="methodparam">void</span> )

retrieve current response object

### Parameters

This function has no parameters.

### Return Values

<span class="classname">Yaf\_Response\_Abstract</span> instance

Yaf\_Controller\_Abstract::getView
==================================

Retrieve the view engine

### Description

<span class="modifier">public</span> <span
class="type">Yaf\_View\_Interface</span> <span
class="methodname">Yaf\_Controller\_Abstract::getView</span> ( <span
class="methodparam">void</span> )

retrieve view engine

### Parameters

This function has no parameters.

### Return Values

Yaf\_Controller\_Abstract::getViewpath
======================================

The getViewpath purpose

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">Yaf\_Controller\_Abstract::getViewpath</span> (
<span class="methodparam">void</span> )

### Parameters

This function has no parameters.

### Return Values

Yaf\_Controller\_Abstract::init
===============================

Controller initializer

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Controller\_Abstract::init</span> ( <span
class="methodparam">void</span> )

<span class="methodname">Yaf\_Controller\_Abstract::\_\_construct</span>
is final, which means users can not override it. but users can define
<span class="methodname">Yaf\_Controller\_Abstract::init</span>, which
will be called after controller object is instantiated.

### Parameters

This function has no parameters.

### Return Values

### See Also

-   <span
    class="methodname">Yaf\_Controller\_Abstract::\_\_construct</span>

Yaf\_Controller\_Abstract::initView
===================================

The initView purpose

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Controller\_Abstract::initView</span> (\[
<span class="methodparam"><span class="type">array</span>
`$options`</span> \] )

### Parameters

`options`  

### Return Values

Yaf\_Controller\_Abstract::redirect
===================================

Redirect to a URL

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Yaf\_Controller\_Abstract::redirect</span> (
<span class="methodparam"><span class="type">string</span> `$url`</span>
)

redirect to a URL by sending a 302 header

### Parameters

`url`  
a location URL

### Return Values

bool

Yaf\_Controller\_Abstract::render
=================================

Render view template

### Description

<span class="modifier">protected</span> <span class="type">string</span>
<span class="methodname">Yaf\_Controller\_Abstract::render</span> (
<span class="methodparam"><span class="type">string</span> `$tpl`</span>
\[, <span class="methodparam"><span class="type">array</span>
`$parameters`</span> \] )

### Parameters

`tpl`  

`parameters`  

### Return Values

Yaf\_Controller\_Abstract::setViewpath
======================================

The setViewpath purpose

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Controller\_Abstract::setViewpath</span> (
<span class="methodparam"><span class="type">string</span>
`$view_directory`</span> )

### Parameters

`view_directory`  

### Return Values

Introduction
------------

A action can be defined in a separate file in Yaf(see <span
class="classname">Yaf\_Controller\_Abstract</span>). that is a action
method can also be a <span
class="classname">Yaf\_Action\_Abstract</span> class.

Since there should be a entry point which can be called by Yaf (as of
PHP 5.3, there is a new magic method \_\_invoke, but Yaf is not only
works with PHP 5.3+, Yaf choose another magic method execute), you must
implement the abstract method <span
class="methodname">Yaf\_Action\_Abstract::execute</span> in your custom
action class.

Class synopsis
--------------

**Yaf\_Action\_Abstract**

<span class="ooclass"> class **Yaf\_Action\_Abstract** </span> <span
class="ooclass"> <span class="modifier">extends</span>
**Yaf\_Controller\_Abstract** </span> {

/\* Properties \*/

<span class="modifier">protected</span> `$_controller` ;

/\* Methods \*/

<span class="modifier">abstract</span> <span
class="modifier">public</span><span class="type">mixed</span> <span
class="methodname">execute</span> (\[ <span class="methodparam"><span
class="type">mixed</span> `$arg`</span> \[, <span
class="methodparam"><span class="type">mixed</span> `$...`</span> \]\] )

<span class="modifier">public</span><span
class="type">Yaf\_Controller\_Abstract</span> <span
class="methodname">getController</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getControllerName</span> ( <span
class="methodparam">void</span> )

/\* Inherited methods \*/

<span class="modifier">final</span> <span
class="modifier">private</span> <span
class="methodname">Yaf\_Controller\_Abstract::\_\_construct</span> (
<span class="methodparam">void</span> )

<span class="modifier">protected</span> <span class="type">bool</span>
<span class="methodname">Yaf\_Controller\_Abstract::display</span> (
<span class="methodparam"><span class="type">string</span> `$tpl`</span>
\[, <span class="methodparam"><span class="type">array</span>
`$parameters`</span> \] )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Controller\_Abstract::forward</span> (
<span class="methodparam"><span class="type">string</span>
`$action`</span> \[, <span class="methodparam"><span
class="type">array</span> `$paramters`</span> \] )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Controller\_Abstract::getInvokeArg</span>
( <span class="methodparam"><span class="type">string</span>
`$name`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Controller\_Abstract::getInvokeArgs</span>
( <span class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">Yaf\_Controller\_Abstract::getModuleName</span>
( <span class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">Yaf\_Controller\_Abstract::getName</span> (
<span class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="type">Yaf\_Request\_Abstract</span> <span
class="methodname">Yaf\_Controller\_Abstract::getRequest</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="type">Yaf\_Response\_Abstract</span> <span
class="methodname">Yaf\_Controller\_Abstract::getResponse</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="type">Yaf\_View\_Interface</span> <span
class="methodname">Yaf\_Controller\_Abstract::getView</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">Yaf\_Controller\_Abstract::getViewpath</span> (
<span class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Controller\_Abstract::init</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Controller\_Abstract::initView</span> (\[
<span class="methodparam"><span class="type">array</span>
`$options`</span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Yaf\_Controller\_Abstract::redirect</span> (
<span class="methodparam"><span class="type">string</span> `$url`</span>
)

<span class="modifier">protected</span> <span class="type">string</span>
<span class="methodname">Yaf\_Controller\_Abstract::render</span> (
<span class="methodparam"><span class="type">string</span> `$tpl`</span>
\[, <span class="methodparam"><span class="type">array</span>
`$parameters`</span> \] )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Controller\_Abstract::setViewpath</span> (
<span class="methodparam"><span class="type">string</span>
`$view_directory`</span> )

}

Properties
----------

`_module`  

`_name`  

`_request`  

`_response`  

`_invoke_args`  

`_view`  

`_controller`  

Yaf\_Action\_Abstract::execute
==============================

Action entry point

### Description

<span class="modifier">abstract</span> <span
class="modifier">public</span><span class="type">mixed</span> <span
class="methodname">Yaf\_Action\_Abstract::execute</span> (\[ <span
class="methodparam"><span class="type">mixed</span> `$arg`</span> \[,
<span class="methodparam"><span class="type">mixed</span> `$...`</span>
\]\] )

user should always define this method for a action, this is the entry
point of an action. <span
class="methodname">Yaf\_Action\_Abstract::execute</span> may have
agruments.

> **Note**:
>
> The value retrived from the request is not safe. you should do some
> filtering work before you use it.

### Parameters

This function has no parameters.

### Return Values

### Examples

**Example \#1 <span
class="function">Yaf\_Action\_Abstract::execute</span>example**

``` php
<?php
/** 
 * A controller example
 */
class ProductController extends Yaf_Controller_Abstract {
      protected $actions = array(
          "index" => "actions/Index.php",
      );
}
?>
```

**Example \#2 <span
class="function">Yaf\_Action\_Abstract::execute</span>example**

``` php
<?php
/** 
 * ListAction
 */
class ListAction extends Yaf_Action_Abstract {
     public function execute ($name, $id) {
         assert($name == $this->getRequest()->getParam("name"));
         assert($id   == $this->getRequest()->getParam("id"));
     }
}
?>
```

The above example will output something similar to:

    /**
     * Now assuming we are using the Yaf_Route_Static route 
     * for request: http://yourdomain/product/list/name/yaf/id/22
     * will result:
     */
     bool(true)
     bool(true)

### See Also

-   

Yaf\_Action\_Abstract::getController
====================================

Retrieve controller object

### Description

<span class="modifier">public</span><span
class="type">Yaf\_Controller\_Abstract</span> <span
class="methodname">Yaf\_Action\_Abstract::getController</span> ( <span
class="methodparam">void</span> )

retrieve current controller object.

### Parameters

This function has no parameters.

### Return Values

<span class="classname">Yaf\_Controller\_Abstract</span> instance

Yaf\_Action\_Abstract::getControllerName
========================================

Get controller name

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">Yaf\_Action\_Abstract::getControllerName</span>
( <span class="methodparam">void</span> )

get the controller's name

### Parameters

This function has no parameters.

### Return Values

<span class="type">string</span>, controller name

Introduction
------------

Yaf provides a ability for developers to use custom view engine instead
of built-in engine which is <span
class="classname">Yaf\_View\_Simple</span>. There is a example to
explain how to do this, please see <span
class="methodname">Yaf\_Dispatcher::setView</span>.

Class synopsis
--------------

**Yaf\_View\_Interface**

<span class="ooclass"> class **Yaf\_View\_Interface** </span> {

/\* Methods \*/

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type">bool</span> <span
class="methodname">assign</span> ( <span class="methodparam"><span
class="type">string</span> `$name`</span> \[, <span
class="methodparam"><span class="type">string</span> `$value`</span> \]
)

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type">bool</span> <span
class="methodname">display</span> ( <span class="methodparam"><span
class="type">string</span> `$tpl`</span> \[, <span
class="methodparam"><span class="type">array</span> `$tpl_vars`</span>
\] )

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type">void</span> <span
class="methodname">getScriptPath</span> ( <span
class="methodparam">void</span> )

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type">string</span> <span
class="methodname">render</span> ( <span class="methodparam"><span
class="type">string</span> `$tpl`</span> \[, <span
class="methodparam"><span class="type">array</span> `$tpl_vars`</span>
\] )

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type">void</span> <span
class="methodname">setScriptPath</span> ( <span
class="methodparam"><span class="type">string</span>
`$template_dir`</span> )

}

Yaf\_View\_Interface::assign
============================

Assign value to View engine

### Description

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type">bool</span> <span
class="methodname">Yaf\_View\_Interface::assign</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> \[,
<span class="methodparam"><span class="type">string</span>
`$value`</span> \] )

Assigan values to View engine, then the value can access directly by
name in template.

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`name`  

`value`  

### Return Values

Yaf\_View\_Interface::display
=============================

Render and output a template

### Description

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type">bool</span> <span
class="methodname">Yaf\_View\_Interface::display</span> ( <span
class="methodparam"><span class="type">string</span> `$tpl`</span> \[,
<span class="methodparam"><span class="type">array</span>
`$tpl_vars`</span> \] )

Render a template and output the result immediatly.

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`tpl`  

`tpl_vars`  

### Return Values

Yaf\_View\_Interface::getScriptPath
===================================

The getScriptPath purpose

### Description

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type">void</span> <span
class="methodname">Yaf\_View\_Interface::getScriptPath</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

Yaf\_View\_Interface::render
============================

Render a template

### Description

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type">string</span> <span
class="methodname">Yaf\_View\_Interface::render</span> ( <span
class="methodparam"><span class="type">string</span> `$tpl`</span> \[,
<span class="methodparam"><span class="type">array</span>
`$tpl_vars`</span> \] )

Render a template and return the result.

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`tpl`  

`tpl_vars`  

### Return Values

Yaf\_View\_Interface::setScriptPath
===================================

The setScriptPath purpose

### Description

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type">void</span> <span
class="methodname">Yaf\_View\_Interface::setScriptPath</span> ( <span
class="methodparam"><span class="type">string</span>
`$template_dir`</span> )

Set the templates base directory, this is usually called by <span
class="classname">Yaf\_Dispatcher</span>

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`template_dir`  
A absolute path to the template directory, by default, <span
class="classname">Yaf\_Dispatcher</span> use
<a href="/yaf/appconfig.html#" class="link">application.directory</a> .
"/views" as this paramter.

### Return Values

Introduction
------------

<span class="classname">Yaf\_View\_Simple</span> is the built-in
template engine in Yaf, it is a simple but fast template engine, and
only support PHP script template.

Class synopsis
--------------

**Yaf\_View\_Simple**

<span class="ooclass"> class **Yaf\_View\_Simple** </span> <span
class="oointerface">implements <span
class="interfacename">Yaf\_View\_Interface</span> </span> {

/\* Properties \*/

<span class="modifier">protected</span> `$_tpl_vars` ;

<span class="modifier">protected</span> `$_tpl_dir` ;

/\* Methods \*/

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">assign</span> ( <span class="methodparam"><span
class="type">string</span> `$name`</span> \[, <span
class="methodparam"><span class="type">mixed</span> `$value`</span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">assignRef</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> ,
<span class="methodparam"><span class="type">mixed</span>
`&$value`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">clear</span> (\[ <span
class="methodparam"><span class="type">string</span> `$name`</span> \] )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="methodname">\_\_construct</span> ( <span
class="methodparam"><span class="type">string</span>
`$template_dir`</span> \[, <span class="methodparam"><span
class="type">array</span> `$options`</span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">display</span> ( <span
class="methodparam"><span class="type">string</span> `$tpl`</span> \[,
<span class="methodparam"><span class="type">array</span>
`$tpl_vars`</span> \] )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">eval</span> ( <span class="methodparam"><span
class="type">string</span> `$tpl_content`</span> \[, <span
class="methodparam"><span class="type">array</span> `$tpl_vars`</span>
\] )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">\_\_get</span> (\[ <span
class="methodparam"><span class="type">string</span> `$name`</span> \] )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getScriptPath</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">\_\_isset</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">render</span> ( <span class="methodparam"><span
class="type">string</span> `$tpl`</span> \[, <span
class="methodparam"><span class="type">array</span> `$tpl_vars`</span>
\] )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">\_\_set</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> ,
<span class="methodparam"><span class="type">mixed</span>
`$value`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setScriptPath</span> ( <span
class="methodparam"><span class="type">string</span>
`$template_dir`</span> )

}

Properties
----------

`_tpl_vars`  

`_tpl_dir`  

Yaf\_View\_Simple::assign
=========================

Assign values

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Yaf\_View\_Simple::assign</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> \[,
<span class="methodparam"><span class="type">mixed</span>
`$value`</span> \] )

assign variable to view engine

### Parameters

`name`  
A string or an array.

if is string, then the next argument $value is required.

`value`  
mixed value

### Return Values

### Examples

**Example \#1 <span
class="function">Yaf\_View\_Simple::assign</span>example**

``` php
<?php
class IndexController extends Yaf_Controller_Abstract {
    public function indexAction() {
        $this->getView()->assign("foo", "bar");
        $this->_view->assign( array( "key" => "value", "name" => "value"));
    }
?>
```

**Example \#2 <span class="function">template</span>example**

``` php
<html>
 <head>
  <title><?php echo $foo; ?></title>
 </head>  
<body>
  <?php 
    foreach ($this->_tpl_vars as $name => value) {
         echo $$name; // or echo $this->_tpl_vars[$name];
    }
  ?>
</body>
</html>
```

### See Also

-   <span class="methodname">Yaf\_View\_Simple::assignRef</span>
-   <span class="methodname">Yaf\_View\_Interface::clear</span>
-   <span class="methodname">Yaf\_View\_Simple::\_\_set</span>

Yaf\_View\_Simple::assignRef
============================

The assignRef purpose

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Yaf\_View\_Simple::assignRef</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> ,
<span class="methodparam"><span class="type">mixed</span>
`&$value`</span> )

unlike <span class="methodname">Yaf\_View\_Simple::assign</span>, this
method assign a ref value to engine.

### Parameters

`name`  
A string name which will be used to access the value in the tempalte.

`value`  
mixed value

### Return Values

### Examples

**Example \#1 <span
class="function">Yaf\_View\_Simple::assignRef</span>example**

``` php
<?php
class IndexController extends Yaf_Controller_Abstract {
    public function indexAction() {
        $value = "bar";
        $this->getView()->assign("foo", $value);

        /* plz note that there was a bug before Yaf 2.1.4, 
         * which make following output "bar";
         */
        $dummy = $this->getView()->render("index/index.phtml");
        echo $value;

        //prevent the auto-render
        Yaf_Dispatcher::getInstance()->autoRender(FALSE);
    }
?>
```

**Example \#2 <span class="function">template</span>example**

``` php
<html>
 <head>
  <title><?php echo $foo;  $foo = "changed"; ?></title>
 </head>  
<body>
</body>
</html>
```

The above example will output something similar to:

    /* access the index controller will result: */
    changed

### See Also

-   <span class="methodname">Yaf\_View\_Simple::assign</span>
-   <span class="methodname">Yaf\_View\_Simple::\_\_set</span>

Yaf\_View\_Simple::clear
========================

Clear Assigned values

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Yaf\_View\_Simple::clear</span> (\[ <span
class="methodparam"><span class="type">string</span> `$name`</span> \] )

clear assigned variable

### Parameters

`name`  
assigned variable name

if empty, will clear all assigned variables

### Return Values

### Examples

**Example \#1 <span
class="function">Yaf\_View\_Simple::clear</span>example**

``` php
<?php
class IndexController extends Yaf_Controller_Abstract {
    public function indexAction() {
        $this->getView()->clear("foo")->clear("bar"); // clear "foo" and "bar"
        $this->_view->clear(); //clear all assigned variables
    }
?>
```

### See Also

-   <span class="methodname">Yaf\_View\_Simple::assignRef</span>
-   <span class="methodname">Yaf\_View\_Interface::assign</span>
-   <span class="methodname">Yaf\_View\_Simple::\_\_set</span>

Yaf\_View\_Simple::\_\_construct
================================

Constructor of Yaf\_View\_Simple

### Description

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="methodname">Yaf\_View\_Simple::\_\_construct</span> ( <span
class="methodparam"><span class="type">string</span>
`$template_dir`</span> \[, <span class="methodparam"><span
class="type">array</span> `$options`</span> \] )

### Parameters

`template_dir`  
The base directory of the templates, by default, it is APPLICATOIN .
"/views" for Yaf.

`options`  
``` parameters
Options for the engine, as of Yaf 2.1.13, you can use short tag
      "<?=$var?>" in your template(regardless of "short_open_tag"), 
      so comes a option named "short_tag",  you can switch this off 
      to prevent use short_tag in template.
```

### Examples

**Example \#1 <span
class="function">Yaf\_View\_Simple::\_\_constructor</span>example**

``` php
<?php
   define ("TEMPLATE_DIRECTORY", APPLICATOIN_PATH . '/views');
   $view = new Yaf_View_Simple(TEMPLATE_DIRECTORY, array(
                           'short_tag' => false //doesn't allow use short tag in template
   ));
?>
```

### Return Values

Yaf\_View\_Simple::display
==========================

Render and display

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Yaf\_View\_Simple::display</span> ( <span
class="methodparam"><span class="type">string</span> `$tpl`</span> \[,
<span class="methodparam"><span class="type">array</span>
`$tpl_vars`</span> \] )

Render a template and display the result instantly.

### Parameters

`tpl`  

`tpl_vars`  

### Return Values

Yaf\_View\_Simple::eval
=======================

Render template

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">Yaf\_View\_Simple::eval</span> ( <span
class="methodparam"><span class="type">string</span>
`$tpl_content`</span> \[, <span class="methodparam"><span
class="type">array</span> `$tpl_vars`</span> \] )

Render a string tempalte and return the result.

### Parameters

`tpl_content`  
string template

`tpl_vars`  

### Return Values

Yaf\_View\_Simple::\_\_get
==========================

Retrieve assigned variable

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_View\_Simple::\_\_get</span> (\[ <span
class="methodparam"><span class="type">string</span> `$name`</span> \] )

Retrieve assigned varaiable

> **Note**:
>
> parameter can be empty since 2.1.11

### Parameters

`name`  
the assigned variable name

if this is empty, all assigned variables will be returned

### Return Values

Yaf\_View\_Simple::getScriptPath
================================

Get templates directory

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">Yaf\_View\_Simple::getScriptPath</span> ( <span
class="methodparam">void</span> )

### Parameters

This function has no parameters.

### Return Values

Yaf\_View\_Simple::\_\_isset
============================

The \_\_isset purpose

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_View\_Simple::\_\_isset</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> )

### Parameters

`name`  

### Return Values

Yaf\_View\_Simple::render
=========================

Render template

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">Yaf\_View\_Simple::render</span> ( <span
class="methodparam"><span class="type">string</span> `$tpl`</span> \[,
<span class="methodparam"><span class="type">array</span>
`$tpl_vars`</span> \] )

Render a template and return the result.

### Parameters

`tpl`  

`tpl_vars`  

### Return Values

Yaf\_View\_Simple::\_\_set
==========================

Set value to engine

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_View\_Simple::\_\_set</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> ,
<span class="methodparam"><span class="type">mixed</span>
`$value`</span> )

This is a alternative and easier way to <span
class="methodname">Yaf\_View\_Simple::assign</span>.

### Parameters

`name`  
A string value name.

`value`  
Mixed value.

### Return Values

### Examples

**Example \#1 <span
class="function">Yaf\_View\_Simple::\_\_set</span>example**

``` php
<?php
class IndexController extends Yaf_Controller_Abstract {
    public function indexAction() {
        $this->getView()->foo = "bar"; // same as assign("foo", "bar");
    }
?>
```

### See Also

-   <span class="methodname">Yaf\_View\_Simple::assignRef</span>
-   <span class="methodname">Yaf\_View\_Interface::assign</span>

Yaf\_View\_Simple::setScriptPath
================================

Set tempaltes directory

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Yaf\_View\_Simple::setScriptPath</span> ( <span
class="methodparam"><span class="type">string</span>
`$template_dir`</span> )

### Parameters

`template_dir`  

### Return Values

Introduction
------------

<span class="classname">Yaf\_Loader</span> introduces a comprehensive
autoloading solution for Yaf.

The first time an instance of <span
class="classname">Yaf\_Application</span> is retrieved, <span
class="classname">Yaf\_Loader</span> will instance a singleton, and
registers itself with spl\_autoload. You retrieve an instance using the
<span class="methodname">Yaf\_Loader::getInstance</span>

<span class="classname">Yaf\_Loader</span> attempt to load a class only
one shot, if failed, depend on
<a href="/yaf/setup.html#" class="link">yaf.use_spl_auload</a>, if this
config is On <span class="methodname">Yaf\_Loader::autoload</span> will
return **`FALSE`**, thus give the chance to other autoload function. if
it is Off (by default), <span
class="methodname">Yaf\_Loader::autoload</span> will return **`TRUE`**,
and more important is that a very useful warning will be triggered (very
useful to find out why a class could not be loaded).

> **Note**:
>
> Please keep yaf.use\_spl\_autoload Off unless there is some library
> have their own autoload mechanism and impossible to rewrite it.

By default, <span class="classname">Yaf\_Loader</span> assume all
library (class defined script) store in the
<a href="/yaf/setup.html#" class="link">global library directory</a>,
which is defined in the php.ini(yaf.library).

If you want <span class="classname">Yaf\_Loader</span> search some
classes(libraries) in the
<a href="/class/yaf-loader.html#" class="link">local class directory</a>(which
is defined in application.ini, and by default, it is
<a href="/yaf/appconfig.html#" class="link">application.directory</a> .
"/library"), you should register the class prefix using the <span
class="methodname">Yaf\_Loader::registerLocalNameSpace</span>

Let's see some examples(assuming APPLICATION\_PATH is
<a href="/yaf/appconfig.html#" class="link">application.directory</a>):

**Example \#1 Config example**

``` shell
// Assuming the following configure in php.ini:
yaf.library = "/global_dir"

//Assuming the following configure in application.ini
application.library = APPLICATION_PATH "/library"
```

Assuming the following local name space is registered:

**Example \#2 Register localnamespace**

``` php
<?php
class Bootstrap extends Yaf_Bootstrap_Abstract{
     public function _initLoader($dispatcher) {
          Yaf_Loader::getInstance()->registerLocalNameSpace(array("Foo", "Bar"));
     }
?>
```

Then the autoload examples:

**Example \#3 Load class example**

``` shell
class Foo_Bar_Test =>
  // APPLICATION_PATH/library/Foo/Bar/Test.php
  
class GLO_Name  =>
  // /global_dir/Glo/Name.php
 
class BarNon_Test
  // /global_dir/Barnon/Test.php
```

As of PHP 5.3, you can use namespace:

**Example \#4 Load namespace class example**

``` shell
class \Foo\Bar\Dummy =>
   // APPLICATION_PATH/library/Foo/Bar/Dummy.php

class \FooBar\Bar\Dummy =>
   // /global_dir/FooBar/Bar/Dummy.php
```

You may noticed that all the folder with the first letter capitalized,
you can make them lowercase by set
<a href="/yaf/setup.html#" class="link">yaf.lowcase_path</a> = On in
php.ini

<span class="classname">Yaf\_Loader</span> is also designed to load the
MVC classes, and the rule is:

**Example \#5 MVC class loading example**

``` shell
Controller Classes =>
// APPLICATION_PATH/controllers/

Model Classes =>
// APPLICATION_PATH/models/

Plugin Classes =>
// APPLICATION_PATH/plugins/
```

Yaf identify a class's suffix(this is by default, you can also change to
the prefix by change the configure
<a href="/yaf/setup.html#" class="link">yaf.name_suffix</a>) to decide
whether it is a MVC class:

**Example \#6 MVC class distinctions**

``` shell
Controller Classes =>
    // ***Controller

Model Classes =>
    // ***Model

Plugin Classes =>
    // ***Plugin
```

some examples:

**Example \#7 MVC loading example**

``` shell
class IndexController
    // APPLICATION_PATH/controllers/Index.php

class DataModel =>
   // APPLICATION_PATH/models/Data.php

class DummyPlugin =>
  // APPLICATION_PATH/plugins/Dummy.php

class A_B_TestModel =>
  // APPLICATION_PATH/models/A/B/Test.php
```

> **Note**:
>
> As of 2.1.18, Yaf supports Controllers autoloading for user script
> side, (which means the autoloading triggered by user php script, eg:
> access a controller static property in Bootstrap or Plugins), but
> autoloader only try to locate controller class script under the
> default module folder, which is "APPLICATION\_PATH/controllers/".

also, the directory will be affected by
<a href="/yaf/setup.html#" class="link">yaf.lowcase_path</a>.

Class synopsis
--------------

**Yaf\_Loader**

<span class="ooclass"> class **Yaf\_Loader** </span> {

/\* Properties \*/

<span class="modifier">protected</span> `$_local_ns` ;

<span class="modifier">protected</span> `$_library` ;

<span class="modifier">protected</span> `$_global_library` ;

<span class="modifier">static</span> `$_instance` ;

/\* Methods \*/

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">autoload</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">clearLocalNamespace</span> ( <span
class="methodparam">void</span> )

<span class="modifier">private</span> <span
class="methodname">\_\_construct</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">void</span> <span
class="methodname">getInstance</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="type">Yaf\_Loader</span> <span
class="methodname">getLibraryPath</span> (\[ <span
class="methodparam"><span class="type">bool</span> `$is_global`<span
class="initializer"> = **`FALSE`**</span></span> \] )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">getLocalNamespace</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getNamespacePath</span> ( <span
class="methodparam"><span class="type">string</span>
`$namespaces`</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">getNamespaces</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">void</span> <span
class="methodname">import</span> ( <span class="methodparam">void</span>
)

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">isLocalName</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">registerLocalNamespace</span> ( <span
class="methodparam"><span class="type">mixed</span> `$prefix`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">registerNamespace</span> ( <span
class="methodparam"><span class="type"><span
class="type">string</span><span class="type">array</span></span>
`$namespaces`</span> \[, <span class="methodparam"><span
class="type">string</span> `$path`</span> \] )

<span class="modifier">public</span> <span
class="type">Yaf\_Loader</span> <span
class="methodname">setLibraryPath</span> ( <span
class="methodparam"><span class="type">string</span> `$directory`</span>
\[, <span class="methodparam"><span class="type">bool</span>
`$is_global`<span class="initializer"> = **`FALSE`**</span></span> \] )

}

Properties
----------

`_local_ns`  

`_library`  
By default, this value is
<a href="/yaf/appconfig.html#" class="link">application.directory</a> .
"/library", you can change this either in the
application.ini(application.library) or call to <span
class="methodname">Yaf\_Loader::setLibraryPath</span>

`_global_library`  

`_instance`  

Yaf\_Loader::autoload
=====================

The autoload purpose

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Loader::autoload</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

Yaf\_Loader::clearLocalNamespace
================================

The clearLocalNamespace purpose

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Loader::clearLocalNamespace</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

Yaf\_Loader::\_\_construct
==========================

The \_\_construct purpose

### Description

<span class="modifier">private</span> <span
class="methodname">Yaf\_Loader::\_\_construct</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

Yaf\_Loader::getInstance
========================

The getInstance purpose

### Description

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">void</span> <span
class="methodname">Yaf\_Loader::getInstance</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

Yaf\_Loader::getLibraryPath
===========================

Get the library path

### Description

<span class="modifier">public</span> <span
class="type">Yaf\_Loader</span> <span
class="methodname">Yaf\_Loader::getLibraryPath</span> (\[ <span
class="methodparam"><span class="type">bool</span> `$is_global`<span
class="initializer"> = **`FALSE`**</span></span> \] )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

Yaf\_Loader::getLocalNamespace
==============================

The getLocalNamespace purpose

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Loader::getLocalNamespace</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

Yaf\_Loader::getNamespacePath
=============================

Retieve path of a registered namespace

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">Yaf\_Loader::getNamespacePath</span> ( <span
class="methodparam"><span class="type">string</span>
`$namespaces`</span> )

retrieve path of a registered namespace

### Parameters

`namespace`  
a string of namespace.

### Return Values

<span class="type">string</span> path, if the namespace is not
registered, then **`NULL`** default library will be returned

### Examples

**Example \#1 <span
class="function">Yaf\_Loader::registerNamespace</span>example**

``` php
<?php
$loader = Yaf_Loader::getInstance("/var/application/lib");
$loader->registerNamespace("\Vendor\PHP", "/var/lib/php");

$loader->getNamespacePath("\Vendor\PHP"); // '/var/lib/php'
$loader->getNamespacePath("\Vendor\JSP"); // '/var/application/lib'

?>
```

Yaf\_Loader::getLocalNamespace
==============================

Retrive all register namespaces info

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">Yaf\_Loader::getNamespaces</span> ( <span
class="methodparam">void</span> )

get registered namespaces info

### Parameters

This function has no parameters.

### Return Values

<span class="type">array</span>

Yaf\_Loader::import
===================

The import purpose

### Description

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">void</span> <span
class="methodname">Yaf\_Loader::import</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

Yaf\_Loader::isLocalName
========================

The isLocalName purpose

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Loader::isLocalName</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

Yaf\_Loader::registerLocalNamespace
===================================

Register local class prefix

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Loader::registerLocalNamespace</span> (
<span class="methodparam"><span class="type">mixed</span>
`$prefix`</span> )

Register local class prefix name, <span
class="classname">Yaf\_Loader</span> search classes in two library
directories, the one is configured via
<a href="/yaf/appconfig.html#" class="link">application.library.directory</a>(in
application.ini) which is called local libraray directory; the other is
configured via <a href="/yaf/setup.html#" class="link">yaf.library</a>
(in php.ini) which is callled global library directory, since it can be
shared by many applications in the same server.

When an autloading is trigger, <span
class="classname">Yaf\_Loader</span> will determine which library
directory should be searched in by exame the prefix name of the missed
classname. If the prefix name is registered as a localnamespack then
look for it in local library directory, otherwise look for it in global
library directory.

> **Note**:
>
> If yaf.library is not configured, then the global library directory is
> assumed to be the local library directory. in that case, all
> autoloading will look for local library directory. But if you want
> your Yaf application be strong, then always register your own classes
> as local classes.

### Parameters

`prefix`  
a string or a array of class name prefix. all class prefix with these
prefix will be loaded in local library path.

### Return Values

bool

### Examples

**Example \#1 <span
class="function">Yaf\_Loader::registerLocalNamespace</span>example**

``` php
<?php
$loader = Yaf_Loader::getInstance('/local/library/', '/global/library');
$loader->registerLocalNamespace("Baidu");
$loader->registerLocalNamespace(array("Sina", "Weibo"));

$loader->autoload("Baidu_Name"); // search in '/local/library/'
$loader->autoload("Sina");       // search '/local/library/'
$loader->autoload("Global_Name");// search in '/global/library/'
$loader->autoload("Foo_Bar");    // search in '/global/library/'

?>
```

Yaf\_Loader::registerNamespace
==============================

Register namespace with searching path

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Yaf\_Loader::registerNamespace</span> ( <span
class="methodparam"><span class="type"><span
class="type">string</span><span class="type">array</span></span>
`$namespaces`</span> \[, <span class="methodparam"><span
class="type">string</span> `$path`</span> \] )

Register a namespace with searching path, <span
class="classname">Yaf\_Loader</span> searchs classes under this
namespace in path, the one is also could be configureded via
<a href="/yaf/appconfig.html#" class="link">application.library.directory.namespace</a>(in
application.ini);

> **Note**:
>
> Yaf still think underline as folder separator.

### Parameters

`namespace`  
a string of namespace, or a array of namespaces with paths.

`path`  
a string of path, it it better to use abosolute path here for
performance

### Return Values

bool

### Examples

**Example \#1 <span
class="function">Yaf\_Loader::registerNamespace</span>example**

``` php
<?php
$loader = Yaf_Loader::getInstance();
$loader->registerNamespace("\Vendor\PHP", "/var/lib/php");
$loader->registerNamespace(array(
     "\Vendor\ASP" => "/var/lib/asp",
     "\Vendor\JSP" => "/usr/lib/vendor/",
));

$loader->autoload("\Vendor\PHP\Dummy");   //load '/var/lib/php/Dummy.php'
$loader->autoload("\Vendor\PHP\Foo_Bar"); //load '/var/lib/php/Foo/Bar.php'
$loader->autoload("\Vendor\JSP\Dummy");   //load '/usr/lib/vendor/Dummy.php'

?>
```

Yaf\_Loader::setLibraryPath
===========================

Change the library path

### Description

<span class="modifier">public</span> <span
class="type">Yaf\_Loader</span> <span
class="methodname">Yaf\_Loader::setLibraryPath</span> ( <span
class="methodparam"><span class="type">string</span> `$directory`</span>
\[, <span class="methodparam"><span class="type">bool</span>
`$is_global`<span class="initializer"> = **`FALSE`**</span></span> \] )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

Introduction
------------

Plugins allow for easy extensibility and customization of the framework.

Plugins are classes. The actual class definition will vary based on the
component -- you may need to implement this interface, but the fact
remains that the plugin is itself a class.

A plugin could be loaded into Yaf by using <span
class="methodname">Yaf\_Dispatcher::registerPlugin</span>, after
registering, All the methods which the plugin implemented according to
this interface, will be called at the proper time.

Examples
--------

**Example \#1 Plugin example**

``` php
<?php
   /* bootstrap class should be defined under ./application/Bootstrap.php */
   class Bootstrap extends Yaf_Bootstrap_Abstract {
        public function _initPlugin(Yaf_Dispatcher $dispatcher) {
            /* register a plugin */
            $dispatcher->registerPlugin(new TestPlugin());
        }
   }

   /* plugin class should be placed under ./application/plugins/ */
   class TestPlugin extends Yaf_Plugin_Abstract {
        public function routerStartup(Yaf_Request_Abstract $request, Yaf_Response_Abstract $response) {
            /* before router 
               in this hook,  user can do some url rewrite */
            var_dump("routerStartup");
        }
        public function routerShutdown(Yaf_Request_Abstract $request, Yaf_Response_Abstract $response) {
            /* router complete 
               in this hook, user can do login check */
            var_dump("routerShutdown");
        }
        public function dispatchLoopStartup(Yaf_Request_Abstract $request, Yaf_Response_Abstract $response) {
            var_dump("dispatchLoopStartup");
        }
        public function preDispatch(Yaf_Request_Abstract $request, Yaf_Response_Abstract $response) {
            var_dump("preDispatch");
        }
        public function postDispatch(Yaf_Request_Abstract $request, Yaf_Response_Abstract $response) {
            var_dump("postDispatch");
        }
        public function dispatchLoopShutdown(Yaf_Request_Abstract $request, Yaf_Response_Abstract $response) {
            /* final hook
               in this hook user can do logging or implement layout */
            var_dump("dispatchLoopShutdown");
        }
   }

   Class IndexController extends Yaf_Controller_Abstract {
        public function indexAction() {
            return FALSE; //prevent rendering
        }
   }

   $config = array(
       "application" => array(
           "directory" => dirname(__FILE__) . "/application/",
       ),
   );
 
   $app = new Yaf_Application($config);
   $app->bootstrap()->run();
?>
```

The above example will output something similar to:

    string(13) "routerStartup"
    string(14) "routerShutdown"
    string(19) "dispatchLoopStartup"
    string(11) "preDispatch"
    string(12) "postDispatch"
    string(20) "dispatchLoopShutdown"

Class synopsis
--------------

**Yaf\_Plugin\_Abstract**

<span class="ooclass"> class **Yaf\_Plugin\_Abstract** </span> {

/\* Methods \*/

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">dispatchLoopShutdown</span> ( <span
class="methodparam"><span class="type">Yaf\_Request\_Abstract</span>
`$request`</span> , <span class="methodparam"><span
class="type">Yaf\_Response\_Abstract</span> `$response`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">dispatchLoopStartup</span> ( <span
class="methodparam"><span class="type">Yaf\_Request\_Abstract</span>
`$request`</span> , <span class="methodparam"><span
class="type">Yaf\_Response\_Abstract</span> `$response`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">postDispatch</span> ( <span
class="methodparam"><span class="type">Yaf\_Request\_Abstract</span>
`$request`</span> , <span class="methodparam"><span
class="type">Yaf\_Response\_Abstract</span> `$response`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">preDispatch</span> ( <span
class="methodparam"><span class="type">Yaf\_Request\_Abstract</span>
`$request`</span> , <span class="methodparam"><span
class="type">Yaf\_Response\_Abstract</span> `$response`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">preResponse</span> ( <span
class="methodparam"><span class="type">Yaf\_Request\_Abstract</span>
`$request`</span> , <span class="methodparam"><span
class="type">Yaf\_Response\_Abstract</span> `$response`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">routerShutdown</span> ( <span
class="methodparam"><span class="type">Yaf\_Request\_Abstract</span>
`$request`</span> , <span class="methodparam"><span
class="type">Yaf\_Response\_Abstract</span> `$response`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">routerStartup</span> ( <span
class="methodparam"><span class="type">Yaf\_Request\_Abstract</span>
`$request`</span> , <span class="methodparam"><span
class="type">Yaf\_Response\_Abstract</span> `$response`</span> )

}

Yaf\_Plugin\_Abstract::dispatchLoopShutdown
===========================================

The dispatchLoopShutdown purpose

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span
class="methodname">Yaf\_Plugin\_Abstract::dispatchLoopShutdown</span> (
<span class="methodparam"><span
class="type">Yaf\_Request\_Abstract</span> `$request`</span> , <span
class="methodparam"><span class="type">Yaf\_Response\_Abstract</span>
`$response`</span> )

This is the latest hook in Yaf plugin hook system, if a custom plugin
implement this method, then it will be called after the dispatch loop
finished.

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`request`  

`response`  

### Return Values

### See Also

-   <span class="methodname">Yaf\_Plugin\_Abstract::routerStartup</span>
-   <span
    class="methodname">Yaf\_Plugin\_Abstract::routerShutdown</span>
-   <span
    class="methodname">Yaf\_Plugin\_Abstract::dispatchLoopStartup</span>
-   <span class="methodname">Yaf\_Plugin\_Abstract::preDispatch</span>
-   <span class="methodname">Yaf\_Plugin\_Abstract::postDispatch</span>

Yaf\_Plugin\_Abstract::dispatchLoopStartup
==========================================

Hook before dispatch loop

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span
class="methodname">Yaf\_Plugin\_Abstract::dispatchLoopStartup</span> (
<span class="methodparam"><span
class="type">Yaf\_Request\_Abstract</span> `$request`</span> , <span
class="methodparam"><span class="type">Yaf\_Response\_Abstract</span>
`$response`</span> )

### Parameters

`request`  

`response`  

### Return Values

Yaf\_Plugin\_Abstract::postDispatch
===================================

The postDispatch purpose

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Plugin\_Abstract::postDispatch</span> (
<span class="methodparam"><span
class="type">Yaf\_Request\_Abstract</span> `$request`</span> , <span
class="methodparam"><span class="type">Yaf\_Response\_Abstract</span>
`$response`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`request`  

`response`  

### Return Values

Yaf\_Plugin\_Abstract::preDispatch
==================================

The preDispatch purpose

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Plugin\_Abstract::preDispatch</span> (
<span class="methodparam"><span
class="type">Yaf\_Request\_Abstract</span> `$request`</span> , <span
class="methodparam"><span class="type">Yaf\_Response\_Abstract</span>
`$response`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`request`  

`response`  

### Return Values

Yaf\_Plugin\_Abstract::preResponse
==================================

The preResponse purpose

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Plugin\_Abstract::preResponse</span> (
<span class="methodparam"><span
class="type">Yaf\_Request\_Abstract</span> `$request`</span> , <span
class="methodparam"><span class="type">Yaf\_Response\_Abstract</span>
`$response`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`request`  

`response`  

### Return Values

Yaf\_Plugin\_Abstract::routerShutdown
=====================================

The routerShutdown purpose

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Plugin\_Abstract::routerShutdown</span> (
<span class="methodparam"><span
class="type">Yaf\_Request\_Abstract</span> `$request`</span> , <span
class="methodparam"><span class="type">Yaf\_Response\_Abstract</span>
`$response`</span> )

This hook will be trigged after the route process finished, this hook is
usually used for login check.

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`request`  

`response`  

### Return Values

### Examples

**Example \#1 <span
class="function">Yaf\_Plugin\_Abstract::routerShutdown</span>example**

``` php
<?php
class UserInitPlugin extends Yaf_Plugin_Abstract {

    public function routerShutdown(Yaf_Request_Abstract $request, Yaf_Response_Abstract $response) {
        $controller = $request->getControllerName();

        /**
         * Use access controller is unecessary for APIs
         */
        if (in_array(strtolower($controller), array(
            'api',  
        ))) {
            return TRUE;
        }
       
        if (Yaf_Session::getInstance()->has("login")) {
            return TRUE;
        }
 
        /* Use access check failed, need to login */
        $response->redirect("http://yourdomain.com/login/");
        return FALSE;
    }
?>
```

### See Also

-   <span class="methodname">Yaf\_Plugin\_Abstract::routerStartup</span>
-   <span
    class="methodname">Yaf\_Plugin\_Abstract::dispatchLoopStartup</span>
-   <span class="methodname">Yaf\_Plugin\_Abstract::preDispatch</span>
-   <span class="methodname">Yaf\_Plugin\_Abstract::postDispatch</span>
-   <span
    class="methodname">Yaf\_Plugin\_Abstract::dispatchLoopShutdown</span>

Yaf\_Plugin\_Abstract::routerStartup
====================================

RouterStartup hook

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Plugin\_Abstract::routerStartup</span> (
<span class="methodparam"><span
class="type">Yaf\_Request\_Abstract</span> `$request`</span> , <span
class="methodparam"><span class="type">Yaf\_Response\_Abstract</span>
`$response`</span> )

This is the earliest hook in Yaf plugin hook system, if a custom plugin
implement this method, then it will be called before routing a request.

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`request`  

`response`  

### Return Values

### See Also

-   <span
    class="methodname">Yaf\_Plugin\_Abstract::routerShutdown</span>
-   <span
    class="methodname">Yaf\_Plugin\_Abstract::dispatchLoopStartup</span>
-   <span class="methodname">Yaf\_Plugin\_Abstract::preDispatch</span>
-   <span class="methodname">Yaf\_Plugin\_Abstract::postDispatch</span>
-   <span
    class="methodname">Yaf\_Plugin\_Abstract::dispatchLoopShutdown</span>

Introduction
------------

All methods of <span class="classname">Yaf\_Registry</span> declared as
static, making it unversally accessible. This provides the ability to
get or set any custom data from anyway in your code as necessary.

Class synopsis
--------------

**Yaf\_Registry**

<span class="ooclass"> class **Yaf\_Registry** </span> {

/\* Properties \*/

<span class="modifier">static</span> `$_instance` ;

<span class="modifier">protected</span> `$_entries` ;

/\* Methods \*/

<span class="modifier">private</span> <span
class="methodname">\_\_construct</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">void</span> <span
class="methodname">del</span> ( <span class="methodparam"><span
class="type">string</span> `$name`</span> )

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">mixed</span> <span
class="methodname">get</span> ( <span class="methodparam"><span
class="type">string</span> `$name`</span> )

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">bool</span> <span
class="methodname">has</span> ( <span class="methodparam"><span
class="type">string</span> `$name`</span> )

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">bool</span> <span
class="methodname">set</span> ( <span class="methodparam"><span
class="type">string</span> `$name`</span> , <span
class="methodparam"><span class="type">string</span> `$value`</span> )

}

Properties
----------

`_instance`  

`_entries`  

Yaf\_Registry::\_\_construct
============================

Yaf\_Registry implements singleton

### Description

<span class="modifier">private</span> <span
class="methodname">Yaf\_Registry::\_\_construct</span> ( <span
class="methodparam">void</span> )

### Parameters

This function has no parameters.

### Return Values

Yaf\_Registry::del
==================

Remove an item from registry

### Description

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">void</span> <span
class="methodname">Yaf\_Registry::del</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> )

Remove an item from registry

### Parameters

`name`  

### Return Values

Yaf\_Registry::get
==================

Retrieve an item from registry

### Description

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">mixed</span> <span
class="methodname">Yaf\_Registry::get</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> )

Retrieve an item from registry

### Parameters

`name`  

### Return Values

Yaf\_Registry::has
==================

Check whether an item exists

### Description

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">bool</span> <span
class="methodname">Yaf\_Registry::has</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> )

Check whether an item exists

### Parameters

`name`  

### Return Values

Yaf\_Registry::set
==================

Add an item into registry

### Description

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">bool</span> <span
class="methodname">Yaf\_Registry::set</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> ,
<span class="methodparam"><span class="type">string</span>
`$value`</span> )

Add an item into registry

### Parameters

`name`  

`value`  

### Return Values

Introduction
------------

Class synopsis
--------------

**Yaf\_Request\_Abstract**

<span class="ooclass"> class **Yaf\_Request\_Abstract** </span> {

/\* Constants \*/

<span class="modifier">const</span> <span class="type">string</span>
`Yaf_Request_Abstract::SCHEME_HTTP` <span class="initializer"> =
http</span> ;

<span class="modifier">const</span> <span class="type">string</span>
`Yaf_Request_Abstract::SCHEME_HTTPS` <span class="initializer"> =
https</span> ;

/\* Properties \*/

<span class="modifier">public</span> `$module` ;

<span class="modifier">public</span> `$controller` ;

<span class="modifier">public</span> `$action` ;

<span class="modifier">public</span> `$method` ;

<span class="modifier">protected</span> `$params` ;

<span class="modifier">protected</span> `$language` ;

<span class="modifier">protected</span> `$_exception` ;

<span class="modifier">protected</span> `$_base_uri` ;

<span class="modifier">protected</span> `$uri` ;

<span class="modifier">protected</span> `$dispatched` ;

<span class="modifier">protected</span> `$routed` ;

/\* Methods \*/

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">clearParams</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">getActionName</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">getBaseUri</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">getControllerName</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">getEnv</span> ( <span class="methodparam"><span
class="type">string</span> `$name`</span> \[, <span
class="methodparam"><span class="type">string</span> `$default`</span>
\] )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">getException</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">getLanguage</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getMethod</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">getModuleName</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">getParam</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> \[,
<span class="methodparam"><span class="type">string</span>
`$default`</span> \] )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">getParams</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">getRequestUri</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">getServer</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> \[,
<span class="methodparam"><span class="type">string</span>
`$default`</span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">isCli</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">isDispatched</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">isGet</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">isHead</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">isOptions</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">isPost</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">isPut</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">isRouted</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">isXmlHttpRequest</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">setActionName</span> ( <span
class="methodparam"><span class="type">string</span> `$action`</span>
\[, <span class="methodparam"><span class="type">bool</span>
`$format_name`<span class="initializer"> = true</span></span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setBaseUri</span> ( <span
class="methodparam"><span class="type">string</span> `$uir`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">setControllerName</span> ( <span
class="methodparam"><span class="type">string</span>
`$controller`</span> \[, <span class="methodparam"><span
class="type">bool</span> `$format_name`<span class="initializer"> =
true</span></span> \] )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">setDispatched</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">setModuleName</span> ( <span
class="methodparam"><span class="type">string</span> `$module`</span>
\[, <span class="methodparam"><span class="type">bool</span>
`$format_name`<span class="initializer"> = true</span></span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setParam</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> \[,
<span class="methodparam"><span class="type">string</span>
`$value`</span> \] )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">setRequestUri</span> ( <span
class="methodparam"><span class="type">string</span> `$uir`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">setRouted</span> (\[ <span
class="methodparam"><span class="type">string</span> `$flag`</span> \] )

}

Properties
----------

`module`  

`controller`  

`action`  

`method`  

`params`  

`language`  

`_exception`  

`_base_uri`  

`uri`  

`dispatched`  

`routed`  

Predefined Constants
--------------------

**`Yaf_Request_Abstract::SCHEME_HTTP`**  

**`Yaf_Request_Abstract::SCHEME_HTTPS`**  

Yaf\_Request\_Abstract::clearParams
===================================

Remove all params

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Yaf\_Request\_Abstract::clearParams</span> (
<span class="methodparam">void</span> )

Remove all params set by router, or <span
class="methodname">Yaf\_Request\_Abstract::setParam</span>

### Parameters

This function has no parameters.

### Return Values

<span class="type">boolean</span>

### See Also

-   <span class="methodname">Yaf\_Request\_Abstract::isHead</span>
-   <span class="methodname">Yaf\_Request\_Abstract::isGet</span>
-   <span class="methodname">Yaf\_Request\_Abstract::isPost</span>
-   <span class="methodname">Yaf\_Request\_Abstract::isPut</span>
-   <span class="methodname">Yaf\_Request\_Abstract::isOptions</span>
-   <span
    class="methodname">Yaf\_Request\_Abstract::isXmlHTTPRequest</span>

Yaf\_Request\_Abstract::getActionName
=====================================

The getActionName purpose

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Request\_Abstract::getActionName</span> (
<span class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

Yaf\_Request\_Abstract::getBaseUri
==================================

The getBaseUri purpose

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Request\_Abstract::getBaseUri</span> (
<span class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

Yaf\_Request\_Abstract::getControllerName
=========================================

The getControllerName purpose

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span
class="methodname">Yaf\_Request\_Abstract::getControllerName</span> (
<span class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

Yaf\_Request\_Abstract::getEnv
==============================

Retrieve ENV varialbe

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Request\_Abstract::getEnv</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> \[,
<span class="methodparam"><span class="type">string</span>
`$default`</span> \] )

Retrieve ENV variable

### Parameters

`name`  
the variable name

`default`  
if this parameter is provide, this will be returned if the varialbe can
not be found

### Return Values

Returns string

### See Also

-   <span class="methodname">Yaf\_Request\_Abstract::getServer</span>
-   <span class="methodname">Yaf\_Request\_Abstract::getParam</span>

Yaf\_Request\_Abstract::getException
====================================

The getException purpose

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Request\_Abstract::getException</span> (
<span class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

Yaf\_Request\_Abstract::getLanguage
===================================

Retrieve client's prefered language

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Request\_Abstract::getLanguage</span> (
<span class="methodparam">void</span> )

### Parameters

This function has no parameters.

### Return Values

Returns a string

Yaf\_Request\_Abstract::getMethod
=================================

Retrieve the request method

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">Yaf\_Request\_Abstract::getMethod</span> (
<span class="methodparam">void</span> )

### Parameters

This function has no parameters.

### Return Values

Return a string, like "POST", "GET" etc.

### See Also

-   <span class="methodname">Yaf\_Request\_Abstract::isHead</span>
-   <span class="methodname">Yaf\_Request\_Abstract::isCli</span>
-   <span class="methodname">Yaf\_Request\_Abstract::isPost</span>
-   <span class="methodname">Yaf\_Request\_Abstract::isPut</span>
-   <span class="methodname">Yaf\_Request\_Abstract::isOptions</span>
-   <span
    class="methodname">Yaf\_Request\_Abstract::isXmlHTTPRequest</span>

Yaf\_Request\_Abstract::getModuleName
=====================================

The getModuleName purpose

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Request\_Abstract::getModuleName</span> (
<span class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

Yaf\_Request\_Abstract::getParam
================================

Retrieve calling parameter

### Description

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">Yaf\_Request\_Abstract::getParam</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> \[,
<span class="methodparam"><span class="type">string</span>
`$default`</span> \] )

### Parameters

`name`  

`default`  

### Return Values

### See Also

-   <span class="methodname">Yaf\_Request\_Abstract::setParam</span>

Yaf\_Request\_Abstract::getParams
=================================

Retrieve all calling parameters

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">Yaf\_Request\_Abstract::getParams</span> (
<span class="methodparam">void</span> )

### Parameters

This function has no parameters.

### Return Values

### See Also

-   <span class="methodname">Yaf\_Request\_Abstract::setParam</span>

Yaf\_Request\_Abstract::getRequestUri
=====================================

The getRequestUri purpose

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Request\_Abstract::getRequestUri</span> (
<span class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

Yaf\_Request\_Abstract::getServer
=================================

Retrieve SERVER variable

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Request\_Abstract::getServer</span> (
<span class="methodparam"><span class="type">string</span>
`$name`</span> \[, <span class="methodparam"><span
class="type">string</span> `$default`</span> \] )

Retrieve SERVER variable

### Parameters

`name`  
the variable name

`default`  
if this parameter is provide, this will be returned if the variable can
not be found

### Return Values

### See Also

-   <span class="methodname">Yaf\_Request\_Abstract::getParam</span>
-   <span class="methodname">Yaf\_Request\_Abstract::getEnv</span>

Yaf\_Request\_Abstract::isCli
=============================

Determine if request is CLI request

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Yaf\_Request\_Abstract::isCli</span> ( <span
class="methodparam">void</span> )

### Parameters

This function has no parameters.

### Return Values

bolean

### See Also

-   <span class="methodname">Yaf\_Request\_Abstract::isHead</span>
-   <span class="methodname">Yaf\_Request\_Abstract::isGet</span>
-   <span class="methodname">Yaf\_Request\_Abstract::isPost</span>
-   <span class="methodname">Yaf\_Request\_Abstract::isPut</span>
-   <span class="methodname">Yaf\_Request\_Abstract::isOptions</span>
-   <span
    class="methodname">Yaf\_Request\_Abstract::isXmlHTTPRequest</span>

Yaf\_Request\_Abstract::isDispatched
====================================

Determin if the request is dispatched

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Yaf\_Request\_Abstract::isDispatched</span> (
<span class="methodparam">void</span> )

### Parameters

This function has no parameters.

### Return Values

boolean

### See Also

-   <span class="methodname">Yaf\_Dispatcher::dispatch</span>

Yaf\_Request\_Abstract::isGet
=============================

Determine if request is GET request

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Yaf\_Request\_Abstract::isGet</span> ( <span
class="methodparam">void</span> )

### Parameters

This function has no parameters.

### Return Values

boolean

### See Also

-   <span class="methodname">Yaf\_Request\_Abstract::isHead</span>
-   <span class="methodname">Yaf\_Request\_Abstract::isCli</span>
-   <span class="methodname">Yaf\_Request\_Abstract::isPost</span>
-   <span class="methodname">Yaf\_Request\_Abstract::isPut</span>
-   <span class="methodname">Yaf\_Request\_Abstract::isOptions</span>
-   <span
    class="methodname">Yaf\_Request\_Abstract::isXmlHTTPRequest</span>

Yaf\_Request\_Abstract::isHead
==============================

Determine if request is HEAD request

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Yaf\_Request\_Abstract::isHead</span> ( <span
class="methodparam">void</span> )

### Parameters

This function has no parameters.

### Return Values

boolean

### See Also

-   <span class="methodname">Yaf\_Request\_Abstract::isGet</span>
-   <span class="methodname">Yaf\_Request\_Abstract::isCli</span>
-   <span class="methodname">Yaf\_Request\_Abstract::isPost</span>
-   <span class="methodname">Yaf\_Request\_Abstract::isPut</span>
-   <span class="methodname">Yaf\_Request\_Abstract::isOptions</span>
-   <span
    class="methodname">Yaf\_Request\_Abstract::isXmlHTTPRequest</span>

Yaf\_Request\_Abstract::isOptions
=================================

Determine if request is OPTIONS request

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Yaf\_Request\_Abstract::isOptions</span> (
<span class="methodparam">void</span> )

### Parameters

This function has no parameters.

### Return Values

boolean

Yaf\_Request\_Abstract::isPost
==============================

Determine if request is POST request

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Yaf\_Request\_Abstract::isPost</span> ( <span
class="methodparam">void</span> )

### Parameters

This function has no parameters.

### Return Values

boolean

### See Also

-   <span class="methodname">Yaf\_Request\_Abstract::isGet</span>
-   <span class="methodname">Yaf\_Request\_Abstract::isCli</span>
-   <span class="methodname">Yaf\_Request\_Abstract::isHead</span>
-   <span class="methodname">Yaf\_Request\_Abstract::isPut</span>
-   <span class="methodname">Yaf\_Request\_Abstract::isOptions</span>
-   <span
    class="methodname">Yaf\_Request\_Abstract::isXmlHTTPRequest</span>

Yaf\_Request\_Abstract::isPut
=============================

Determine if request is PUT request

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Yaf\_Request\_Abstract::isPut</span> ( <span
class="methodparam">void</span> )

### Parameters

This function has no parameters.

### Return Values

boolean

### See Also

-   <span class="methodname">Yaf\_Request\_Abstract::isHead</span>
-   <span class="methodname">Yaf\_Request\_Abstract::isCli</span>
-   <span class="methodname">Yaf\_Request\_Abstract::isPost</span>
-   <span class="methodname">Yaf\_Request\_Abstract::isGet</span>
-   <span class="methodname">Yaf\_Request\_Abstract::isOptions</span>
-   <span
    class="methodname">Yaf\_Request\_Abstract::isXmlHTTPRequest</span>

Yaf\_Request\_Abstract::isRouted
================================

Determin if request has been routed

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Yaf\_Request\_Abstract::isRouted</span> ( <span
class="methodparam">void</span> )

### Parameters

This function has no parameters.

### Return Values

boolean

Yaf\_Request\_Abstract::isXmlHttpRequest
========================================

Determine if request is AJAX request

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Yaf\_Request\_Abstract::isXmlHttpRequest</span>
( <span class="methodparam">void</span> )

### Parameters

This function has no parameters.

### Return Values

boolean

### See Also

-   <span class="methodname">Yaf\_Request\_Abstract::isHead</span>
-   <span class="methodname">Yaf\_Request\_Abstract::isCli</span>
-   <span class="methodname">Yaf\_Request\_Abstract::isPost</span>
-   <span class="methodname">Yaf\_Request\_Abstract::isPut</span>
-   <span class="methodname">Yaf\_Request\_Abstract::isOptions</span>
-   <span class="methodname">Yaf\_Request\_Abstract::isGet</span>

Yaf\_Request\_Abstract::setActionName
=====================================

Set action name

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Request\_Abstract::setActionName</span> (
<span class="methodparam"><span class="type">string</span>
`$action`</span> \[, <span class="methodparam"><span
class="type">bool</span> `$format_name`<span class="initializer"> =
true</span></span> \] )

set action name to request, this is usually used by custom router to set
route result controller name.

### Parameters

`action`  
<span class="type">string</span>, action name, it should in lower case
style, like "index" or "foo\_bar"

`format_name`  
this is introduced in Yaf 3.2.0, by default Yaf will format the name
into lower case style, if this is set to **`FALSE`** , Yaf will set the
original name to request.

### Return Values

Yaf\_Request\_Abstract::setBaseUri
==================================

Set base URI

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Yaf\_Request\_Abstract::setBaseUri</span> (
<span class="methodparam"><span class="type">string</span> `$uir`</span>
)

Set base URI, base URI is used when doing routing, in routing phase
request URI is used to route a request, while base URI is used to skip
the leadding part(base URI) of request URI. That is, if comes a request
with request URI a/b/c, then if you set base URI to "a/b", only "/c"
will be used in routing phase.

> **Note**:
>
> generally, you don't need to set this, Yaf will determine it
> automatically.

### Parameters

`uir`  
base URI

### Return Values

bool

Yaf\_Request\_Abstract::setControllerName
=========================================

Set controller name

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span
class="methodname">Yaf\_Request\_Abstract::setControllerName</span> (
<span class="methodparam"><span class="type">string</span>
`$controller`</span> \[, <span class="methodparam"><span
class="type">bool</span> `$format_name`<span class="initializer"> =
true</span></span> \] )

set controller name to request, this is usually used by custom router to
set route result controller name.

### Parameters

`controller`  
<span class="type">string</span>, controller name, this should be in
camel style, like "Index" or "Foo\_Bar"

`format_name`  
this is introduced in Yaf 3.2.0, by default Yaf will format the name
into camel mode, if this is set to **`FALSE`** , Yaf will set the
original name to request.

### Return Values

Yaf\_Request\_Abstract::setDispatched
=====================================

The setDispatched purpose

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Request\_Abstract::setDispatched</span> (
<span class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

Yaf\_Request\_Abstract::setModuleName
=====================================

Set module name

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Request\_Abstract::setModuleName</span> (
<span class="methodparam"><span class="type">string</span>
`$module`</span> \[, <span class="methodparam"><span
class="type">bool</span> `$format_name`<span class="initializer"> =
true</span></span> \] )

set module name to request, this is usually used by custom router to set
route result module name.

### Parameters

`module`  
<span class="type">string</span> module name, it should be in camel
style, like "Index" or "Foo\_Bar"

`format_name`  
this is introduced in Yaf 3.2.0, by default Yaf will format the name
into camel mode, if this is set to **`FALSE`** , Yaf will set the
original name to request.

### Return Values

Yaf\_Request\_Abstract::setParam
================================

Set a calling parameter to a request

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Yaf\_Request\_Abstract::setParam</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> \[,
<span class="methodparam"><span class="type">string</span>
`$value`</span> \] )

Set a parameter to request, which can be retrieved by <span
class="methodname">Yaf\_Request\_Abstract::getParam</span>

### Parameters

`name`  

`value`  

### Return Values

### See Also

-   <span class="methodname">Yaf\_Request\_Abstract::getParam</span>
-   <span class="methodname">Yaf\_Request\_Abstract::getParams</span>

Yaf\_Request\_Abstract::setRequestUri
=====================================

The setRequestUri purpose

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Request\_Abstract::setRequestUri</span> (
<span class="methodparam"><span class="type">string</span> `$uir`</span>
)

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`uir`  

### Return Values

Yaf\_Request\_Abstract::setRouted
=================================

The setRouted purpose

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Request\_Abstract::setRouted</span> (\[
<span class="methodparam"><span class="type">string</span>
`$flag`</span> \] )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`flag`  

### Return Values

Introduction
------------

Any request from client is initialized as a <span
class="classname">Yaf\_Request\_Http</span>. you can get the request
information like, uri query and post parameters via methods of this
class.

> **Note**:
>
> For security, $\_GET/$\_POST are readonly in Yaf, which means if you
> set a value to these global variables, you can not get it from <span
> class="methodname">Yaf\_Request\_Http::getQuery</span> or <span
> class="methodname">Yaf\_Request\_Http::getPost</span>.
>
> But there do is some usage need such feature, like unit testing. thus
> Yaf can be built with --enable-yaf-debug, which will allow Yaf read
> the value user set via script.
>
> in such case, Yaf will throw a E\_STRICT warning to remind you about
> that: Strict Standards: you are running yaf in debug mode

Class synopsis
--------------

**Yaf\_Request\_Http**

<span class="ooclass"> class **Yaf\_Request\_Http** </span> <span
class="ooclass"> <span class="modifier">extends</span>
**Yaf\_Request\_Abstract** </span> {

/\* Properties \*/

/\* Methods \*/

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> (\[ <span
class="methodparam"><span class="type">string</span>
`$request_uri`</span> \[, <span class="methodparam"><span
class="type">string</span> `$base_uri`</span> \]\] )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">get</span> ( <span class="methodparam"><span
class="type">string</span> `$name`</span> \[, <span
class="methodparam"><span class="type">string</span> `$default`</span>
\] )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">getCookie</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> \[,
<span class="methodparam"><span class="type">string</span>
`$default`</span> \] )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">getFiles</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">getPost</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> \[,
<span class="methodparam"><span class="type">string</span>
`$default`</span> \] )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">getQuery</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> \[,
<span class="methodparam"><span class="type">string</span>
`$default`</span> \] )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">getRaw</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">getRequest</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">isXmlHttpRequest</span> ( <span
class="methodparam">void</span> )

/\* Inherited methods \*/

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Yaf\_Request\_Abstract::clearParams</span> (
<span class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Request\_Abstract::getActionName</span> (
<span class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Request\_Abstract::getBaseUri</span> (
<span class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span
class="methodname">Yaf\_Request\_Abstract::getControllerName</span> (
<span class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Request\_Abstract::getEnv</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> \[,
<span class="methodparam"><span class="type">string</span>
`$default`</span> \] )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Request\_Abstract::getException</span> (
<span class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Request\_Abstract::getLanguage</span> (
<span class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">Yaf\_Request\_Abstract::getMethod</span> (
<span class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Request\_Abstract::getModuleName</span> (
<span class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">Yaf\_Request\_Abstract::getParam</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> \[,
<span class="methodparam"><span class="type">string</span>
`$default`</span> \] )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">Yaf\_Request\_Abstract::getParams</span> (
<span class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Request\_Abstract::getRequestUri</span> (
<span class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Request\_Abstract::getServer</span> (
<span class="methodparam"><span class="type">string</span>
`$name`</span> \[, <span class="methodparam"><span
class="type">string</span> `$default`</span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Yaf\_Request\_Abstract::isCli</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Yaf\_Request\_Abstract::isDispatched</span> (
<span class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Yaf\_Request\_Abstract::isGet</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Yaf\_Request\_Abstract::isHead</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Yaf\_Request\_Abstract::isOptions</span> (
<span class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Yaf\_Request\_Abstract::isPost</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Yaf\_Request\_Abstract::isPut</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Yaf\_Request\_Abstract::isRouted</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Yaf\_Request\_Abstract::isXmlHttpRequest</span>
( <span class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Request\_Abstract::setActionName</span> (
<span class="methodparam"><span class="type">string</span>
`$action`</span> \[, <span class="methodparam"><span
class="type">bool</span> `$format_name`<span class="initializer"> =
true</span></span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Yaf\_Request\_Abstract::setBaseUri</span> (
<span class="methodparam"><span class="type">string</span> `$uir`</span>
)

<span class="modifier">public</span> <span class="type">void</span>
<span
class="methodname">Yaf\_Request\_Abstract::setControllerName</span> (
<span class="methodparam"><span class="type">string</span>
`$controller`</span> \[, <span class="methodparam"><span
class="type">bool</span> `$format_name`<span class="initializer"> =
true</span></span> \] )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Request\_Abstract::setDispatched</span> (
<span class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Request\_Abstract::setModuleName</span> (
<span class="methodparam"><span class="type">string</span>
`$module`</span> \[, <span class="methodparam"><span
class="type">bool</span> `$format_name`<span class="initializer"> =
true</span></span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Yaf\_Request\_Abstract::setParam</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> \[,
<span class="methodparam"><span class="type">string</span>
`$value`</span> \] )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Request\_Abstract::setRequestUri</span> (
<span class="methodparam"><span class="type">string</span> `$uir`</span>
)

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Request\_Abstract::setRouted</span> (\[
<span class="methodparam"><span class="type">string</span>
`$flag`</span> \] )

}

Properties
----------

`module`  

`controller`  

`action`  

`method`  

`params`  

`language`  

`_exception`  

`_base_uri`  

`uri`  

`dispatched`  

`routed`  

Yaf\_Request\_Http::\_\_construct
=================================

Constructor of Yaf\_Request\_Http

### Description

<span class="modifier">public</span> <span
class="methodname">Yaf\_Request\_Http::\_\_construct</span> (\[ <span
class="methodparam"><span class="type">string</span>
`$request_uri`</span> \[, <span class="methodparam"><span
class="type">string</span> `$base_uri`</span> \]\] )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

Yaf\_Request\_Http::get
=======================

Retrieve variable from client

### Description

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">Yaf\_Request\_Http::get</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> \[,
<span class="methodparam"><span class="type">string</span>
`$default`</span> \] )

Retrieve variable from client, this method will search the `name` in
request pramas, if the name is not found, then will search in POST, GET,
Cookie, Server

### Parameters

`name`  
the variable name

`default`  
if this parameter is provide, this will be returned if the varialbe can
not be found

### Return Values

### See Also

-   <span class="methodname">Yaf\_Request\_Http::getQuery</span>
-   <span class="methodname">Yaf\_Request\_Http::getPost</span>
-   <span class="methodname">Yaf\_Request\_Http::getCookie</span>
-   <span class="methodname">Yaf\_Request\_Http::getRaw</span>
-   <span class="methodname">Yaf\_Request\_Abstract::getServer</span>
-   <span class="methodname">Yaf\_Request\_Abstract::getParam</span>

Yaf\_Request\_Http::getCookie
=============================

Retrieve Cookie variable

### Description

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">Yaf\_Request\_Http::getCookie</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> \[,
<span class="methodparam"><span class="type">string</span>
`$default`</span> \] )

Retrieve Cookie variable

### Parameters

`name`  
the cookie name

`default`  
if this parameter is provide, this will be returned if the cookie can
not be found

### Return Values

### See Also

-   <span class="methodname">Yaf\_Request\_Http::get</span>
-   <span class="methodname">Yaf\_Request\_Http::getQuery</span>
-   <span class="methodname">Yaf\_Request\_Http::getPost</span>
-   <span class="methodname">Yaf\_Request\_Http::getRaw</span>
-   <span class="methodname">Yaf\_Request\_Abstract::getServer</span>
-   <span class="methodname">Yaf\_Request\_Abstract::getParam</span>

Yaf\_Request\_Http::getFiles
============================

The getFiles purpose

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Request\_Http::getFiles</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

Yaf\_Request\_Http::getPost
===========================

Retrieve POST variable

### Description

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">Yaf\_Request\_Http::getPost</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> \[,
<span class="methodparam"><span class="type">string</span>
`$default`</span> \] )

Retrieve POST variable

### Parameters

`name`  
the variable name

`default`  
if this parameter is provide, this will be returned if the varialbe can
not be found

### Return Values

### See Also

-   <span class="methodname">Yaf\_Request\_Http::get</span>
-   <span class="methodname">Yaf\_Request\_Http::getQuery</span>
-   <span class="methodname">Yaf\_Request\_Http::getCookie</span>
-   <span class="methodname">Yaf\_Request\_Http::getRaw</span>
-   <span class="methodname">Yaf\_Request\_Abstract::getServer</span>
-   <span class="methodname">Yaf\_Request\_Abstract::getParam</span>

Yaf\_Request\_Http::getQuery
============================

Fetch a query parameter

### Description

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">Yaf\_Request\_Http::getQuery</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> \[,
<span class="methodparam"><span class="type">string</span>
`$default`</span> \] )

Retrieve GET variable

### Parameters

`name`  
the variable name

`default`  
if this parameter is provide, this will be returned if the variable can
not be found

### Return Values

### See Also

-   <span class="methodname">Yaf\_Request\_Http::get</span>
-   <span class="methodname">Yaf\_Request\_Http::getPost</span>
-   <span class="methodname">Yaf\_Request\_Http::getCookie</span>
-   <span class="methodname">Yaf\_Request\_Http::getRaw</span>
-   <span class="methodname">Yaf\_Request\_Abstract::getServer</span>
-   <span class="methodname">Yaf\_Request\_Abstract::getParam</span>

Yaf\_Request\_Http::getRaw
==========================

Retrieve Raw request body

### Description

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">Yaf\_Request\_Http::getRaw</span> ( <span
class="methodparam">void</span> )

Retrieve Raw request body

### Parameters

This function has no parameters.

### Return Values

Return string on success, FALSE on failure.

### See Also

-   <span class="methodname">Yaf\_Request\_Http::get</span>
-   <span class="methodname">Yaf\_Request\_Http::getPost</span>
-   <span class="methodname">Yaf\_Request\_Http::getCookie</span>
-   <span class="methodname">Yaf\_Request\_Http::getQuery</span>
-   <span class="methodname">Yaf\_Request\_Abstract::getServer</span>
-   <span class="methodname">Yaf\_Request\_Abstract::getParam</span>

Yaf\_Request\_Http::getRequest
==============================

The getRequest purpose

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Request\_Http::getRequest</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

Yaf\_Request\_Http::isXmlHttpRequest
====================================

Determin if request is Ajax Request

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Yaf\_Request\_Http::isXmlHttpRequest</span> (
<span class="methodparam">void</span> )

Check the request whether it is a Ajax Request.

> **Note**:
>
> This method depends on the request header: HTTP\_X\_REQUESTED\_WITH,
> some Javascript library doesn't set this header while doing Ajax
> request

### Parameters

This function has no parameters.

### Return Values

boolean

Introduction
------------

<span class="classname">Yaf\_Request\_Simple</span> is particularlly
used for test puporse. ie. simulate some espacial request under CLI
mode.

Class synopsis
--------------

**Yaf\_Request\_Simple**

<span class="ooclass"> class **Yaf\_Request\_Simple** </span> <span
class="ooclass"> <span class="modifier">extends</span>
**Yaf\_Request\_Abstract** </span> {

/\* Constants \*/

<span class="modifier">const</span> <span class="type">string</span>
`Yaf_Request_Simple::SCHEME_HTTP` <span class="initializer"> =
http</span> ;

<span class="modifier">const</span> <span class="type">string</span>
`Yaf_Request_Simple::SCHEME_HTTPS` <span class="initializer"> =
https</span> ;

/\* Properties \*/

/\* Methods \*/

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> (\[ <span
class="methodparam"><span class="type">string</span> `$method`</span>
\[, <span class="methodparam"><span class="type">string</span>
`$module`</span> \[, <span class="methodparam"><span
class="type">string</span> `$controller`</span> \[, <span
class="methodparam"><span class="type">string</span> `$action`</span>
\[, <span class="methodparam"><span class="type">array</span>
`$params`</span> \]\]\]\]\] )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">get</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">getCookie</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">getFiles</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">getPost</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">getQuery</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">getRequest</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">isXmlHttpRequest</span> ( <span
class="methodparam">void</span> )

/\* Inherited methods \*/

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Yaf\_Request\_Abstract::clearParams</span> (
<span class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Request\_Abstract::getActionName</span> (
<span class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Request\_Abstract::getBaseUri</span> (
<span class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span
class="methodname">Yaf\_Request\_Abstract::getControllerName</span> (
<span class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Request\_Abstract::getEnv</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> \[,
<span class="methodparam"><span class="type">string</span>
`$default`</span> \] )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Request\_Abstract::getException</span> (
<span class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Request\_Abstract::getLanguage</span> (
<span class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">Yaf\_Request\_Abstract::getMethod</span> (
<span class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Request\_Abstract::getModuleName</span> (
<span class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">Yaf\_Request\_Abstract::getParam</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> \[,
<span class="methodparam"><span class="type">string</span>
`$default`</span> \] )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">Yaf\_Request\_Abstract::getParams</span> (
<span class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Request\_Abstract::getRequestUri</span> (
<span class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Request\_Abstract::getServer</span> (
<span class="methodparam"><span class="type">string</span>
`$name`</span> \[, <span class="methodparam"><span
class="type">string</span> `$default`</span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Yaf\_Request\_Abstract::isCli</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Yaf\_Request\_Abstract::isDispatched</span> (
<span class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Yaf\_Request\_Abstract::isGet</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Yaf\_Request\_Abstract::isHead</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Yaf\_Request\_Abstract::isOptions</span> (
<span class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Yaf\_Request\_Abstract::isPost</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Yaf\_Request\_Abstract::isPut</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Yaf\_Request\_Abstract::isRouted</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Yaf\_Request\_Abstract::isXmlHttpRequest</span>
( <span class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Request\_Abstract::setActionName</span> (
<span class="methodparam"><span class="type">string</span>
`$action`</span> \[, <span class="methodparam"><span
class="type">bool</span> `$format_name`<span class="initializer"> =
true</span></span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Yaf\_Request\_Abstract::setBaseUri</span> (
<span class="methodparam"><span class="type">string</span> `$uir`</span>
)

<span class="modifier">public</span> <span class="type">void</span>
<span
class="methodname">Yaf\_Request\_Abstract::setControllerName</span> (
<span class="methodparam"><span class="type">string</span>
`$controller`</span> \[, <span class="methodparam"><span
class="type">bool</span> `$format_name`<span class="initializer"> =
true</span></span> \] )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Request\_Abstract::setDispatched</span> (
<span class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Request\_Abstract::setModuleName</span> (
<span class="methodparam"><span class="type">string</span>
`$module`</span> \[, <span class="methodparam"><span
class="type">bool</span> `$format_name`<span class="initializer"> =
true</span></span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Yaf\_Request\_Abstract::setParam</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> \[,
<span class="methodparam"><span class="type">string</span>
`$value`</span> \] )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Request\_Abstract::setRequestUri</span> (
<span class="methodparam"><span class="type">string</span> `$uir`</span>
)

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Request\_Abstract::setRouted</span> (\[
<span class="methodparam"><span class="type">string</span>
`$flag`</span> \] )

}

Properties
----------

`module`  

`controller`  

`action`  

`method`  

`params`  

`language`  

`_exception`  

`_base_uri`  

`uri`  

`dispatched`  

`routed`  

Predefined Constants
--------------------

**`Yaf_Request_Simple::SCHEME_HTTP`**  

**`Yaf_Request_Simple::SCHEME_HTTPS`**  

Yaf\_Request\_Simple::\_\_construct
===================================

Constructor of Yaf\_Request\_Simple

### Description

<span class="modifier">public</span> <span
class="methodname">Yaf\_Request\_Simple::\_\_construct</span> (\[ <span
class="methodparam"><span class="type">string</span> `$method`</span>
\[, <span class="methodparam"><span class="type">string</span>
`$module`</span> \[, <span class="methodparam"><span
class="type">string</span> `$controller`</span> \[, <span
class="methodparam"><span class="type">string</span> `$action`</span>
\[, <span class="methodparam"><span class="type">array</span>
`$params`</span> \]\]\]\]\] )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

Yaf\_Request\_Simple::get
=========================

The get purpose

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Request\_Simple::get</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

Yaf\_Request\_Simple::getCookie
===============================

The getCookie purpose

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Request\_Simple::getCookie</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

Yaf\_Request\_Simple::getFiles
==============================

The getFiles purpose

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Request\_Simple::getFiles</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

Yaf\_Request\_Simple::getPost
=============================

The getPost purpose

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Request\_Simple::getPost</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

Yaf\_Request\_Simple::getQuery
==============================

The getQuery purpose

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Request\_Simple::getQuery</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

Yaf\_Request\_Simple::getRequest
================================

The getRequest purpose

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Request\_Simple::getRequest</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

Yaf\_Request\_Simple::isXmlHttpRequest
======================================

Determin if request is AJAX request

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Request\_Simple::isXmlHttpRequest</span> (
<span class="methodparam">void</span> )

### Parameters

This function has no parameters.

### Return Values

Always returns false for <span
class="classname">Yaf\_Request\_Simple</span>

### See Also

-   <span
    class="methodname">Yaf\_Request\_Abstract::isXmlHTTPRequest</span>
-   <span class="methodname">Yaf\_Request\_Http::isXmlHTTPRequest</span>

Introduction
------------

Class synopsis
--------------

**Yaf\_Response\_Abstract**

<span class="ooclass"> class **Yaf\_Response\_Abstract** </span> {

/\* Constants \*/

<span class="modifier">const</span> <span class="type">string</span>
`Yaf_Response_Abstract::DEFAULT_BODY` <span class="initializer"> =
"content"</span> ;

/\* Properties \*/

<span class="modifier">protected</span> `$_header` ;

<span class="modifier">protected</span> `$_body` ;

<span class="modifier">protected</span> `$_sendheader` ;

/\* Methods \*/

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">appendBody</span> ( <span
class="methodparam"><span class="type">string</span> `$content`</span>
\[, <span class="methodparam"><span class="type">string</span>
`$key`</span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">clearBody</span> (\[ <span
class="methodparam"><span class="type">string</span> `$key`</span> \] )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">clearHeaders</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">\_\_destruct</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">getBody</span> (\[ <span
class="methodparam"><span class="type">string</span> `$key`</span> \] )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">getHeader</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">prependBody</span> ( <span
class="methodparam"><span class="type">string</span> `$content`</span>
\[, <span class="methodparam"><span class="type">string</span>
`$key`</span> \] )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">response</span> ( <span
class="methodparam">void</span> )

<span class="modifier">protected</span> <span class="type">void</span>
<span class="methodname">setAllHeaders</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setBody</span> ( <span
class="methodparam"><span class="type">string</span> `$content`</span>
\[, <span class="methodparam"><span class="type">string</span>
`$key`</span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setHeader</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> ,
<span class="methodparam"><span class="type">string</span>
`$value`</span> \[, <span class="methodparam"><span
class="type">bool</span> `$replace`</span> \] )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">setRedirect</span> ( <span
class="methodparam">void</span> )

<span class="modifier">private</span> <span class="type">string</span>
<span class="methodname">\_\_toString</span> ( <span
class="methodparam">void</span> )

}

Properties
----------

`_header`  

`_body`  

`_sendheader`  

Yaf\_Response\_Abstract::appendBody
===================================

Append to response body

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Yaf\_Response\_Abstract::appendBody</span> (
<span class="methodparam"><span class="type">string</span>
`$content`</span> \[, <span class="methodparam"><span
class="type">string</span> `$key`</span> \] )

Append a content to a exists content block

### Parameters

`body`  
content string

`key`  
the content key, you can set a content with a key, if you don't
specific, then Yaf\_Response\_Abstract::DEFAULT\_BODY will be used

> **Note**:
>
> this parameter is introduced as of 2.2.0

### Return Values

bool

### Examples

**Example \#1 <span
class="function">Yaf\_Response\_Abstract::appendBody</span>example**

``` php
<?php
$response = new Yaf_Response_Http();

$response->setBody("Hello")->prependBody(" World");

echo $response;
?>
```

The above example will output something similar to:

    Hello World

### See Also

-   <span class="classname">Yaf\_Config\_Ini</span>

### See Also

-   <span class="methodname">Yaf\_Response\_Abstract::getBody</span>
-   <span class="methodname">Yaf\_Response\_Abstract::setBody</span>
-   <span class="methodname">Yaf\_Response\_Abstract::prependBody</span>
-   <span class="methodname">Yaf\_Response\_Abstract::clearBody</span>

Yaf\_Response\_Abstract::clearBody
==================================

Discard all exists response body

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Yaf\_Response\_Abstract::clearBody</span> (\[
<span class="methodparam"><span class="type">string</span> `$key`</span>
\] )

Clear existsed content

### Parameters

`key`  
the content key, if you don't specific, then all contents will be
cleared.

> **Note**:
>
> this parameter is introduced as of 2.2.0

### Return Values

### See Also

-   <span class="methodname">Yaf\_Response\_Abstract::setBody</span>
-   <span class="methodname">Yaf\_Response\_Abstract::appendBody</span>
-   <span class="methodname">Yaf\_Response\_Abstract::prependBody</span>
-   <span class="methodname">Yaf\_Response\_Abstract::getBody</span>

Yaf\_Response\_Abstract::clearHeaders
=====================================

Discard all set headers

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Response\_Abstract::clearHeaders</span> (
<span class="methodparam">void</span> )

### Parameters

This function has no parameters.

### Return Values

### See Also

-   <span class="methodname">Yaf\_Response\_Abstract::getHeader</span>
-   <span class="methodname">Yaf\_Response\_Abstract::setHeader</span>

Yaf\_Response\_Abstract::\_\_construct
======================================

The \_\_construct purpose

### Description

<span class="modifier">public</span> <span
class="methodname">Yaf\_Response\_Abstract::\_\_construct</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

Yaf\_Response\_Abstract::\_\_destruct
=====================================

The \_\_destruct purpose

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Response\_Abstract::\_\_destruct</span> (
<span class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

Yaf\_Response\_Abstract::getBody
================================

Retrieve a exists content

### Description

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">Yaf\_Response\_Abstract::getBody</span> (\[
<span class="methodparam"><span class="type">string</span> `$key`</span>
\] )

Retrieve a exists content

### Parameters

`key`  
the content key, if you don't specific, then
Yaf\_Response\_Abstract::DEFAULT\_BODY will be used. if you pass in a
**`NULL`**, then all contents will be returned as a array

> **Note**:
>
> this parameter is introduced as of 2.2.0

### Return Values

### Examples

**Example \#1 <span
class="function">Yaf\_Response\_Abstract::getBody</span>example**

``` php
<?php
$response = new Yaf_Response_Http();

$response->setBody("Hello")->setBody(" World", "footer");

var_dump($response->getBody()); //default 
var_dump($response->getBody(Yaf_Response_Abstract::DEFAULT_BODY)); //same as above
var_dump($response->getBody("footer"));
var_dump($response->getBody(NULL)); //get all
?>
```

The above example will output something similar to:

    string(5) "Hello"
    string(5) "Hello"
    string(6) " World"
    array(2) {
      ["content"]=>
      string(5) "Hello"
      ["footer"]=>
      string(6) " World"
    }

### See Also

-   <span class="methodname">Yaf\_Response\_Abstract::setBody</span>
-   <span class="methodname">Yaf\_Response\_Abstract::appendBody</span>
-   <span class="methodname">Yaf\_Response\_Abstract::prependBody</span>
-   <span class="methodname">Yaf\_Response\_Abstract::clearBody</span>

Yaf\_Response\_Abstract::getHeader
==================================

The getHeader purpose

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Response\_Abstract::getHeader</span> (
<span class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

### See Also

-   <span class="methodname">Yaf\_Response\_Abstract::setHeader</span>
-   <span
    class="methodname">Yaf\_Response\_Abstract::cleanHeaders</span>

Yaf\_Response\_Abstract::prependBody
====================================

The prependBody purpose

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Yaf\_Response\_Abstract::prependBody</span> (
<span class="methodparam"><span class="type">string</span>
`$content`</span> \[, <span class="methodparam"><span
class="type">string</span> `$key`</span> \] )

prepend a content to a exists content block

### Parameters

`body`  
content string

`key`  
the content key, you can set a content with a key, if you don't
specific, then Yaf\_Response\_Abstract::DEFAULT\_BODY will be used

> **Note**:
>
> this parameter is introduced as of 2.2.0

### Return Values

bool

### Examples

**Example \#1 <span
class="function">Yaf\_Response\_Abstract::prependBody</span>example**

``` php
<?php
$response = new Yaf_Response_Http();

$response->setBody("World")->prependBody("Hello ");

echo $response;
?>
```

The above example will output something similar to:

    Hello World

### See Also

-   <span class="methodname">Yaf\_Response\_Abstract::getBody</span>
-   <span class="methodname">Yaf\_Response\_Abstract::setBody</span>
-   <span class="methodname">Yaf\_Response\_Abstract::appendBody</span>
-   <span class="methodname">Yaf\_Response\_Abstract::clearBody</span>

Yaf\_Response\_Abstract::response
=================================

Send response

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Response\_Abstract::response</span> (
<span class="methodparam">void</span> )

send response

### Parameters

This function has no parameters.

### Return Values

### Examples

**Example \#1 <span
class="function">Yaf\_Response\_Abstract::response</span>example**

``` php
<?php
$response = new Yaf_Response_Http();

$response->setBody("Hello")->setBody(" World", "footer");

$response->response();
?>
```

The above example will output something similar to:

    Hello World

### See Also

-   <span class="methodname">Yaf\_Response\_Abstract::setBody</span>
-   <span class="methodname">Yaf\_Response\_Abstract::clearBody</span>

Yaf\_Response\_Abstract::setAllHeaders
======================================

The setAllHeaders purpose

### Description

<span class="modifier">protected</span> <span class="type">void</span>
<span class="methodname">Yaf\_Response\_Abstract::setAllHeaders</span> (
<span class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

Yaf\_Response\_Abstract::setBody
================================

Set content to response

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Yaf\_Response\_Abstract::setBody</span> ( <span
class="methodparam"><span class="type">string</span> `$content`</span>
\[, <span class="methodparam"><span class="type">string</span>
`$key`</span> \] )

Set content to response

### Parameters

`body`  
content string

`key`  
the content key, you can set a content with a key, if you don't
specific, then Yaf\_Response\_Abstract::DEFAULT\_BODY will be used

> **Note**:
>
> this parameter is introduced as of 2.2.0

### Return Values

### Examples

**Example \#1 <span
class="function">Yaf\_Response\_Abstract::setBody</span>example**

``` php
<?php
$response = new Yaf_Response_Http();

$response->setBody("Hello")->setBody(" World", "footer");

print_r($response);
echo $response;
?>
```

The above example will output something similar to:

    Yaf_Response_Http Object
    (
        [_header:protected] => Array
            (
            )

        [_body:protected] => Array
            (
                [content] => Hello
                [footer] =>  World
            )

        [_sendheader:protected] => 1
        [_response_code:protected] => 200
    )
    Hello World

### See Also

-   <span class="methodname">Yaf\_Response\_Abstract::getBody</span>
-   <span class="methodname">Yaf\_Response\_Abstract::appendBody</span>
-   <span class="methodname">Yaf\_Response\_Abstract::prependBody</span>
-   <span class="methodname">Yaf\_Response\_Abstract::clearBody</span>

Yaf\_Response\_Abstract::setHeader
==================================

Set reponse header

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Yaf\_Response\_Abstract::setHeader</span> (
<span class="methodparam"><span class="type">string</span>
`$name`</span> , <span class="methodparam"><span
class="type">string</span> `$value`</span> \[, <span
class="methodparam"><span class="type">bool</span> `$replace`</span> \]
)

Used to send a HTTP header

### Parameters

This function has no parameters.

### Return Values

### See Also

-   <span class="methodname">Yaf\_Response\_Abstract::getHeader</span>
-   <span
    class="methodname">Yaf\_Response\_Abstract::cleanHeaders</span>

Yaf\_Response\_Abstract::setRedirect
====================================

The setRedirect purpose

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Response\_Abstract::setRedirect</span> (
<span class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

Yaf\_Response\_Abstract::\_\_toString
=====================================

Retrieve all bodys as string

### Description

<span class="modifier">private</span> <span class="type">string</span>
<span class="methodname">Yaf\_Response\_Abstract::\_\_toString</span> (
<span class="methodparam">void</span> )

### Parameters

This function has no parameters.

### Return Values

Introduction
------------

<span class="classname">Yaf\_Route\_Interface</span> used for developer
defined their custom route.

Class synopsis
--------------

**Yaf\_Route\_Interface**

<span class="ooclass"> class **Yaf\_Route\_Interface** </span> {

/\* Methods \*/

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type">string</span> <span
class="methodname">assemble</span> ( <span class="methodparam"><span
class="type">array</span> `$info`</span> \[, <span
class="methodparam"><span class="type">array</span> `$query`</span> \] )

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type">bool</span> <span
class="methodname">route</span> ( <span class="methodparam"><span
class="type">Yaf\_Request\_Abstract</span> `$request`</span> )

}

Yaf\_Route\_Interface::assemble
===============================

Assemble a request

### Description

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type">string</span> <span
class="methodname">Yaf\_Route\_Interface::assemble</span> ( <span
class="methodparam"><span class="type">array</span> `$info`</span> \[,
<span class="methodparam"><span class="type">array</span>
`$query`</span> \] )

this method returns a url according to the argument info, and append
query strings to the url according to the argument query.

a route should implement this method according to its own route rules,
and do a reverse progress.

### Parameters

`info`  

`query`  

### Return Values

Yaf\_Route\_Interface::route
============================

Route a request

### Description

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type">bool</span> <span
class="methodname">Yaf\_Route\_Interface::route</span> ( <span
class="methodparam"><span class="type">Yaf\_Request\_Abstract</span>
`$request`</span> )

<span class="methodname">Yaf\_Route\_Interface::route</span> is the only
method that a custom route should implement.

> **Note**:
>
> since of 2.3.0, there is another method should also be implemented,
> see <span class="methodname">Yaf\_Route\_Interface::assemble</span>.

if this method return **`TRUE`**, then the route process will be end.
otherwise, <span class="classname">Yaf\_Router</span> will call next
route in the route stack to route request.

This method would set the route result to the parameter request, by
calling <span
class="methodname">Yaf\_Request\_Abstract::setControllerName</span>,
<span class="methodname">Yaf\_Request\_Abstract::setActionName</span>
and <span
class="methodname">Yaf\_Request\_Abstract::setModuleName</span>.

This method should also call <span
class="methodname">Yaf\_Request\_Abstract::setRouted</span> to make the
request routed at last.

### Parameters

`request`  
A <span class="classname">Yaf\_Request\_Abstract</span> instance.

### Return Values

Introduction
------------

<span class="classname">Yaf\_Route\_Map</span> is a built-in route, it
simply convert a URI endpoint (that part of the URI which comes after
the base URI: see <span
class="methodname">Yaf\_Request\_Abstract::setBaseUri</span>) to a
controller name or action name(depends on the parameter passed to <span
class="methodname">Yaf\_Route\_Map::\_\_construct</span>) in following
rule: A =\> controller A. A/B/C =\> controller A\_B\_C. A/B/C/D/E =\>
controller A\_B\_C\_D\_E.

If the second parameter of <span
class="methodname">Yaf\_Route\_Map::\_\_construct</span> is specified,
then only the part before delimiter of URI will used to routing, the
part after it is used to routing request parameters (see the example
section of <span
class="methodname">Yaf\_Route\_Map::\_\_construct</span>).

Class synopsis
--------------

**Yaf\_Route\_Map**

<span class="ooclass"> class **Yaf\_Route\_Map** </span> <span
class="oointerface">implements <span
class="interfacename">Yaf\_Route\_Interface</span> </span> {

/\* Properties \*/

<span class="modifier">protected</span> `$_ctl_router` ;

<span class="modifier">protected</span> `$_delimiter` ;

/\* Methods \*/

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">assemble</span> ( <span
class="methodparam"><span class="type">array</span> `$info`</span> \[,
<span class="methodparam"><span class="type">array</span>
`$query`</span> \] )

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> (\[ <span
class="methodparam"><span class="type">string</span>
`$controller_prefer`<span class="initializer"> =
**`FALSE`**</span></span> \[, <span class="methodparam"><span
class="type">string</span> `$delimiter`<span class="initializer"> =
""</span></span> \]\] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">route</span> ( <span class="methodparam"><span
class="type">Yaf\_Request\_Abstract</span> `$request`</span> )

}

Properties
----------

`_ctl_router`  

`_delimiter`  

Yaf\_Route\_Map::assemble
=========================

Assemble a url

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">Yaf\_Route\_Map::assemble</span> ( <span
class="methodparam"><span class="type">array</span> `$info`</span> \[,
<span class="methodparam"><span class="type">array</span>
`$query`</span> \] )

Assemble a url.

### Parameters

`info`  

`query`  

### Examples

**Example \#1 <span
class="function">Yaf\_Route\_Map::assemble</span>example**

``` php
<?php

$router = new Yaf_Router();

$route  = new Yaf_Route_Map();

$router->addRoute("map", $route);

var_dump($router->getRoute('map')->assemble(
                        array(
                                ':c' => 'foo_bar'
                        ),
                        array(
                                'tkey1' => 'tval1',
                                'tkey2' => 'tval2'
                        )
                   )
);

$route = new Yaf_Route_Map(true, '_');
$router->addRoute("map", $route);

var_dump($router->getRoute('map')->assemble(
                        array(
                                ':a' => 'foo_bar'
                        ),
                        array(
                                'tkey1' => 'tval1',
                                'tkey2' => 'tval2'
                        )
                   )
);
```

The above example will output something similar to:

    string(%d) "/foo/bar?tkey1=tval1&tkey2=tval2"
    string(%d) "/foo/bar/_/tkey1/tval1/tkey2/tval2"

### Return Values

Yaf\_Route\_Map::\_\_construct
==============================

The \_\_construct purpose

### Description

<span class="modifier">public</span> <span
class="methodname">Yaf\_Route\_Map::\_\_construct</span> (\[ <span
class="methodparam"><span class="type">string</span>
`$controller_prefer`<span class="initializer"> =
**`FALSE`**</span></span> \[, <span class="methodparam"><span
class="type">string</span> `$delimiter`<span class="initializer"> =
""</span></span> \]\] )

### Parameters

`controller_prefer`  
Whether the result should considering as controller or action

`delimiter`  

### Return Values

### Examples

**Example \#1 <span class="function">Yaf\_Route\_Map</span>example**

``` php
<?php
   /**
    * Add a map route to Yaf_Router route stack
    */
    Yaf_Dispatcher::getInstance()->getRouter()->addRoute("name",
        new Yaf_Route_Map());
?>
```

The above example will output something similar to:

    /* for http://yourdomain.com/product/foo/bar
     * route will result in following values:
     */
    array(
      "controller" => "product_foo_bar",
    )

**Example \#2 <span class="function">Yaf\_Route\_Map</span>example**

``` php
<?php
   /**
    * Add a map route to Yaf_Router route stack
    */
    Yaf_Dispatcher::getInstance()->getRouter()->addRoute("name",
        new Yaf_Route_Map(true, "_"));
?>
```

The above example will output something similar to:

    /* for http://yourdomain.com/user/list/_/foo/22
     * route will result in following values:
     */
    array(
        "action" => "user_list",
    )

    /**
     * and request parameters:
     */
    array(
      "foo"   => 22,
    )

**Example \#3 <span class="function">Yaf\_Route\_Map</span>example**

``` php
<?php
   /**
    * Add a map route to Yaf_Router route stack by calling addconfig
    */
    $config = array(
        "name" => array(
           "type"  => "map",         //Yaf_Route_Map route
           "controllerPrefer" => FALSE,
           "delimiter"        => "#!", 
           ),
    );
    Yaf_Dispatcher::getInstance()->getRouter()->addConfig(
        new Yaf_Config_Simple($config));
?>
```

### See Also

-   <span class="methodname">Yaf\_Router::addRoute</span>
-   <span class="classname">Yaf\_Route\_Static</span>
-   <span class="classname">Yaf\_Route\_Supervar</span>
-   <span class="classname">Yaf\_Route\_Simple</span>
-   <span class="classname">Yaf\_Route\_Regex</span>
-   <span class="classname">Yaf\_Route\_Rewrite</span>

Yaf\_Route\_Map::route
======================

The route purpose

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Yaf\_Route\_Map::route</span> ( <span
class="methodparam"><span class="type">Yaf\_Request\_Abstract</span>
`$request`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`request`  

### Return Values

Introduction
------------

<span class="classname">Yaf\_Route\_Regex</span> is the most flexible
route among the Yaf built-in routes.

Class synopsis
--------------

**Yaf\_Route\_Regex**

<span class="ooclass"> class **Yaf\_Route\_Regex** </span> <span
class="ooclass"> <span class="modifier">extends</span>
**Yaf\_Route\_Interface** </span> <span class="oointerface">implements
<span class="interfacename">Yaf\_Route\_Interface</span> </span> {

/\* Properties \*/

<span class="modifier">protected</span> `$_route` ;

<span class="modifier">protected</span> `$_default` ;

<span class="modifier">protected</span> `$_maps` ;

<span class="modifier">protected</span> `$_verify` ;

/\* Methods \*/

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">assemble</span> ( <span
class="methodparam"><span class="type">array</span> `$info`</span> \[,
<span class="methodparam"><span class="type">array</span>
`$query`</span> \] )

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> ( <span
class="methodparam"><span class="type">string</span> `$match`</span> ,
<span class="methodparam"><span class="type">array</span>
`$route`</span> \[, <span class="methodparam"><span
class="type">array</span> `$map`</span> \[, <span
class="methodparam"><span class="type">array</span> `$verify`</span> \[,
<span class="methodparam"><span class="type">string</span>
`$reverse`</span> \]\]\] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">route</span> ( <span class="methodparam"><span
class="type">Yaf\_Request\_Abstract</span> `$request`</span> )

/\* Inherited methods \*/

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type">string</span> <span
class="methodname">Yaf\_Route\_Interface::assemble</span> ( <span
class="methodparam"><span class="type">array</span> `$info`</span> \[,
<span class="methodparam"><span class="type">array</span>
`$query`</span> \] )

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type">bool</span> <span
class="methodname">Yaf\_Route\_Interface::route</span> ( <span
class="methodparam"><span class="type">Yaf\_Request\_Abstract</span>
`$request`</span> )

}

Properties
----------

`_route`  

`_default`  

`_maps`  

`_verify`  

Yaf\_Route\_Regex::assemble
===========================

Assemble a url

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">Yaf\_Route\_Regex::assemble</span> ( <span
class="methodparam"><span class="type">array</span> `$info`</span> \[,
<span class="methodparam"><span class="type">array</span>
`$query`</span> \] )

Assemble a url.

### Parameters

`info`  

`query`  

### Examples

**Example \#1 <span
class="function">Yaf\_Route\_Regex::assemble</span>example**

``` php
<?php

$router = new Yaf_Router();

$route  = new Yaf_Route_Regex(
            "#^/product/([^/]+)/([^/])+#",
            array(
                'controller' => "product",  //route to product controller,
                ),
            array(),
            array(),
            '/:m/:c/:a'
        );

$router->addRoute("regex", $route);

var_dump($router->getRoute('regex')->assemble(
            array(
                ':m' => 'module',
                ':c' => 'controller',
                ':a' => 'action'
                ),
            array(
                'tkey1' => 'tval1',
                'tkey2' =>
                'tval2'
                )
            )
        );
```

The above example will output something similar to:

    string(49) "/module/controller/action?tkey1=tval1&tkey2=tval2"

### Return Values

Yaf\_Route\_Regex::\_\_construct
================================

Yaf\_Route\_Regex constructor

### Description

<span class="modifier">public</span> <span
class="methodname">Yaf\_Route\_Regex::\_\_construct</span> ( <span
class="methodparam"><span class="type">string</span> `$match`</span> ,
<span class="methodparam"><span class="type">array</span>
`$route`</span> \[, <span class="methodparam"><span
class="type">array</span> `$map`</span> \[, <span
class="methodparam"><span class="type">array</span> `$verify`</span> \[,
<span class="methodparam"><span class="type">string</span>
`$reverse`</span> \]\]\] )

### Parameters

`match`  
A complete Regex pattern, will be used to match a request uri, if
doesn't matched, <span class="classname">Yaf\_Route\_Regex</span> will
return **`FALSE`**.

`route`  
When the match pattern matches the request uri, <span
class="classname">Yaf\_Route\_Regex</span> will use this to decide which
m/c/a to routed.

either of m/c/a in this array is optianl, if you don't assgian a
specific value, it will be routed to default.

`map`  
A array to assign name to the captrues in the match result.

`verify`  

`reverse`  
a string, used to assemble url, see <span
class="methodname">Yaf\_Route\_Regex::assemble</span>.

> **Note**:
>
> this parameter is introduced in 2.3.0

### Return Values

### Examples

**Example \#1 <span class="function">Yaf\_Route\_Regex</span>example**

``` php
<?php
   /**
    * Add a regex route to Yaf_Router route stack
    */
    Yaf_Dispatcher::getInstance()->getRouter()->addRoute("name",
        new Yaf_Route_Regex(
           "#^/product/([^/]+)/([^/])+#", //match request uri leading "/product"
           array(
               'controller' => "product",  //route to product controller,
           ),
           array(
              1 => "name",   // now you can call $request->getParam("name")
              2 => "id",     // to get the first captrue in the match pattern.
           )
        )
    );
?>
```

**Example \#2 <span class="function">Yaf\_Route\_Regex(as of
2.3.0)</span>example**

``` php
<?php
   /**
    * Use match result as MVC name
    */
    Yaf_Dispatcher::getInstance()->getRouter()->addRoute("name",
        new Yaf_Route_Regex(
           "#^/product/([^/]+)/([^/])+#i", //match request uri leading "/product"
           array(
              'controller' => ":name", // route to :name, which is $1 in the match result as controller name
           ),
           array(
              1 => "name",   // now you can call $request->getParam("name")
              2 => "id",     // to get the first captrue in the match pattern.
           )
        )
    );
?>
```

**Example \#3 <span class="function">Yaf\_Route\_Regex and named capture
ground(as of 2.3.0)</span>example**

``` php
<?php
   /**
    * Use match result as MVC name
    */
    Yaf_Dispatcher::getInstance()->getRouter()->addRoute("name",
        new Yaf_Route_Regex(
           "#^/product/(?<name>[^/]+)/([^/])+#i", //match request uri leading "/product"
           array(
           'controller' => ":name", // route to :name,
                                    // which is named capture group 'name' in the match result as controller name
           ),
           array(
              2 => "id",     // to get the first captrue in the match pattern.
           )
        )
    );
?>
```

**Example \#4 <span class="function">Yaf\_Route\_Regex</span>example**

``` php
<?php
   /**
    * Add a regex route to Yaf_Router route stack by calling addconfig
    */
    $config = array(
        "name" => array(
           "type"  => "regex",          //Yaf_Route_Regex route
           "match" => "#(.*)#",         //match arbitrary request uri
           "route" => array(
               'controller' => "product",  //route to product controller,
               'action'     => "dummy",    //route to dummy action
           ),
           "map" => array(
              1 => "uri",   // now you can call $request->getParam("uri")
           ),
        ),
    );
    Yaf_Dispatcher::getInstance()->getRouter()->addConfig(
        new Yaf_Config_Simple($config));
?>
```

### See Also

-   <span class="methodname">Yaf\_Router::addRoute</span>
-   <span class="methodname">Yaf\_Router::addConfig</span>
-   <span class="classname">Yaf\_Route\_Static</span>
-   <span class="classname">Yaf\_Route\_Supervar</span>
-   <span class="classname">Yaf\_Route\_Simple</span>
-   <span class="classname">Yaf\_Route\_Rewrite</span>
-   <span class="classname">Yaf\_Route\_Map</span>

Yaf\_Route\_Regex::route
========================

The route purpose

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Yaf\_Route\_Regex::route</span> ( <span
class="methodparam"><span class="type">Yaf\_Request\_Abstract</span>
`$request`</span> )

Route a incoming request.

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`request`  

### Return Values

If the pattern given by the first parameter of <span
class="methodname">Yaf\_Route\_Regex::\_construct</span> matche the
request uri, return **`TRUE`**, otherwise return **`FALSE`**.

Introduction
------------

For usage, please see the example section of <span
class="methodname">Yaf\_Route\_Rewrite::\_\_construct</span>

Class synopsis
--------------

**Yaf\_Route\_Rewrite**

<span class="ooclass"> class **Yaf\_Route\_Rewrite** </span> <span
class="ooclass"> <span class="modifier">extends</span>
**Yaf\_Route\_Interface** </span> <span class="oointerface">implements
<span class="interfacename">Yaf\_Route\_Interface</span> </span> {

/\* Properties \*/

<span class="modifier">protected</span> `$_route` ;

<span class="modifier">protected</span> `$_default` ;

<span class="modifier">protected</span> `$_verify` ;

/\* Methods \*/

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">assemble</span> ( <span
class="methodparam"><span class="type">array</span> `$info`</span> \[,
<span class="methodparam"><span class="type">array</span>
`$query`</span> \] )

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> ( <span
class="methodparam"><span class="type">string</span> `$match`</span> ,
<span class="methodparam"><span class="type">array</span>
`$route`</span> \[, <span class="methodparam"><span
class="type">array</span> `$verify`</span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">route</span> ( <span class="methodparam"><span
class="type">Yaf\_Request\_Abstract</span> `$request`</span> )

/\* Inherited methods \*/

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type">string</span> <span
class="methodname">Yaf\_Route\_Interface::assemble</span> ( <span
class="methodparam"><span class="type">array</span> `$info`</span> \[,
<span class="methodparam"><span class="type">array</span>
`$query`</span> \] )

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type">bool</span> <span
class="methodname">Yaf\_Route\_Interface::route</span> ( <span
class="methodparam"><span class="type">Yaf\_Request\_Abstract</span>
`$request`</span> )

}

Properties
----------

`_route`  

`_default`  

`_verify`  

Yaf\_Route\_Rewrite::assemble
=============================

Assemble a url

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">Yaf\_Route\_Rewrite::assemble</span> ( <span
class="methodparam"><span class="type">array</span> `$info`</span> \[,
<span class="methodparam"><span class="type">array</span>
`$query`</span> \] )

Assemble a url.

### Parameters

`info`  

`query`  

### Examples

**Example \#1 <span
class="function">Yaf\_Route\_Rewrite::assemble</span>example**

``` php
router = new Yaf_Router();

$route  = new Yaf_Route_Rewrite(
                "/product/:name/:id/*",
                array(
                        'controller' => "product",
                ),
                array()
);

$router->addRoute("rewrite", $route);

var_dump($router->getRoute('rewrite')->assemble(
                        array(
                                ':name' => 'foo',
                                ':id' => 'bar',
                                ':tmpkey1' => 'tmpval1'
                        ),
                        array(
                                'tkey1' => 'tval1',
                                'tkey2' => 'tval2'
                             )
                        )
);
```

The above example will output something similar to:

    string(57) "/product/foo/bar/tmpkey1/tmpval1/?tkey1=tval1&tkey2=tval2"

### Return Values

Yaf\_Route\_Rewrite::\_\_construct
==================================

Yaf\_Route\_Rewrite constructor

### Description

<span class="modifier">public</span> <span
class="methodname">Yaf\_Route\_Rewrite::\_\_construct</span> ( <span
class="methodparam"><span class="type">string</span> `$match`</span> ,
<span class="methodparam"><span class="type">array</span>
`$route`</span> \[, <span class="methodparam"><span
class="type">array</span> `$verify`</span> \] )

### Parameters

`match`  
A pattern, will be used to match a request uri, if it doesn't match,
<span class="classname">Yaf\_Route\_Rewrite</span> will return
**`FALSE`**.

You can use :name style to name segments matched, and use \* to match
the rest of the URL segments.

`route`  
When the match pattern matches the request uri, <span
class="classname">Yaf\_Route\_Rewrite</span> will use this to decide
which module/controller/action is the destination.

Either of module/controller/action in this array is optional, if you
don't assign a specific value, it will be routed to default.

`verify`  

### Return Values

### Examples

**Example \#1 <span class="function">Yaf\_Route\_Rewrite</span>example**

``` php
<?php
   /**
    * Add a rewrite route to Yaf_Router route stack
    */
    Yaf_Dispatcher::getInstance()->getRouter()->addRoute("name",
        new Yaf_Route_rewrite(
           "/product/:name/:id/*", //match request uri leading "/product"
           array(
               'controller' => "product",  //route to product controller,
           ),
        )
    );
?>
```

The above example will output something similar to:

    /* for http://yourdomain.com/product/foo/22/foo/bar
     * route will result in following values:
     */
    array(
      "controller" => "product",
      "module"     => "index", //(default)
      "action"     => "index", //(default)
    )

    /**
     * and request parameters:
     */
    array(
      "name" => "foo",
      "id"   => 22,
      "foo"  => bar
    )

**Example \#2 <span class="function">Yaf\_Route\_Rewrite</span>example**

``` php
<?php
   /**
    * Add a rewrite route to Yaf_Router route stack by calling addconfig
    */
    $config = array(
        "name" => array(
           "type"  => "rewrite",        //Yaf_Route_Rewrite route
           "match" => "/user-list/:id", //match only /user/list/?/
           "route" => array(
               'controller' => "user",  //route to user controller,
               'action'     => "list",  //route to list action
           ),
        ),
    );
    Yaf_Dispatcher::getInstance()->getRouter()->addConfig(
        new Yaf_Config_Simple($config));
?>
```

The above example will output something similar to:

    /* for http://yourdomain.com/user-list/22
     * route will result in following values:
     */
    array(
      "controller" => "user",
      "action"     => "list",
      "module"     => "index", //(default)
    )

    /**
     * and request parameters:
     */
    array(
      "id"   => 22,
    )

**Example \#3 <span class="function">Yaf\_Route\_Rewrite(as of
2.3.0)</span>example**

``` php
<?php
   /**
    * Add a rewrite route use match result as m/c/a name
    */
    $config = array(
        "name" => array(
           "type"  => "rewrite",        
           "match" => "/user-list/:a/:id", //match only /user-list/*
           "route" => array(
               'controller' => "user",   //route to user controller,
               'action'     => ":a",     //route to :a action
           ),
        ),
    );
    Yaf_Dispatcher::getInstance()->getRouter()->addConfig(
        new Yaf_Config_Simple($config));
?>
```

The above example will output something similar to:

    /* for http://yourdomain.com/user-list/list/22
     * route will result in following values:
     */
    array(
      "controller" => "user",
      "action"     => "list",
      "module"     => "index", //(default)
    )

    /**
     * and request parameters:
     */
    array(
      "id"   => 22,
    )

### See Also

-   <span class="methodname">Yaf\_Router::addRoute</span>
-   <span class="methodname">Yaf\_Router::addConfig</span>
-   <span class="classname">Yaf\_Route\_Static</span>
-   <span class="classname">Yaf\_Route\_Supervar</span>
-   <span class="classname">Yaf\_Route\_Simple</span>
-   <span class="classname">Yaf\_Route\_Regex</span>
-   <span class="classname">Yaf\_Route\_Map</span>

Yaf\_Route\_Rewrite::route
==========================

The route purpose

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Yaf\_Route\_Rewrite::route</span> ( <span
class="methodparam"><span class="type">Yaf\_Request\_Abstract</span>
`$request`</span> )

### Parameters

`request`  

### Return Values

Introduction
------------

<span class="classname">Yaf\_Router</span> is the standard framework
router. Routing is the process of taking a URI endpoint (that part of
the URI which comes after the base URI: see <span
class="methodname">Yaf\_Request\_Abstract::setBaseUri</span>) and
decomposing it into parameters to determine which module, controller,
and action of that controller should receive the request. This values of
the module, controller, action and other parameters are packaged into a
<span class="classname">Yaf\_Request\_Abstract</span> object which is
then processed by <span class="classname">Yaf\_Dispatcher</span>.
Routing occurs only once: when the request is initially received and
before the first controller is dispatched. <span
class="classname">Yaf\_Router</span> is designed to allow for
mod\_rewrite-like functionality using pure PHP structures. It is very
loosely based on Ruby on Rails routing and does not require any prior
knowledge of webserver URL rewriting. It is designed to work with a
single Apache mod\_rewrite rule (one of):

**Example \#1 Rewrite rule for Apache**

``` conf
RewriteEngine on
RewriteRule !\.(js|ico|gif|jpg|png|css|html)$ index.php
```

or (preferred):

**Example \#2 Rewrite rule for Apache**

``` conf
RewriteEngine On
RewriteCond %{REQUEST_FILENAME} -s [OR]
RewriteCond %{REQUEST_FILENAME} -l [OR]
RewriteCond %{REQUEST_FILENAME} -d
RewriteRule ^.*$ - [NC,L]
RewriteRule ^.*$ index.php [NC,L]
```

If using Lighttpd, the following rewrite rule is valid:

**Example \#3 Rewrite rule for Lighttpd**

``` conf
url.rewrite-once = (
  ".*\?(.*)$" => "/index.php?$1",
  ".*\.(js|ico|gif|jpg|png|css|html)$" => "$0",
  "" => "/index.php"
)
```

If using Nginx, use the following rewrite rule:

**Example \#4 Rewrite rule for Nginx**

``` conf
server {
  listen ****;
  server_name  yourdomain.com;
  root   document_root;
  index  index.php index.html;

  if (!-e $request_filename) {
    rewrite ^/(.*)  /index.php/$1 last;
  }
}
```

Default route
-------------

<span class="classname">Yaf\_Router</span> comes preconfigured with a
default route <span class="classname">Yaf\_Route\_Static</span>, which
will match URIs in the shape of controller/action. Additionally, a
module name may be specified as the first path element, allowing URIs of
the form module/controller/action. Finally, it will also match any
additional parameters appended to the URI by default -
controller/action/var1/value1/var2/value2.

> **Note**:
>
> Module name must be defined in config, considering
> application.module="Index,Foo,Bar", in this case, only index, foo and
> bar can be considered as a module name. if doesn't config, there is
> only one module named "Index".

Some examples of how such routes are matched:

**Example \#5 <span class="classname">Yaf\_Route\_Static</span>(default
route)example**

``` conf
// Assuming the following configure:
$conf = array(
   "application" => array(
      "modules" => "Index,Blog",
   ),
);

Controller only:
http://example/news
    controller == news
Action only(when defined yaf.action_prefer=1 in php.ini)
    action  == news
 
Invalid module maps to controller name:
http://example/foo
    controller == foo
 
Module + controller:
http://example/blog/archive
    module     == blog
    controller == archive
 
Module + controller + action:
http://example/blog/archive/list
    module     == blog
    controller == archive
    action     == list
 
Module + controller + action + params:
http://example/blog/archive/list/sort/alpha/date/desc
    module     == blog
    controller == archive
    action     == list
    sort       == alpha
    date       == desc
```

Class synopsis
--------------

**Yaf\_Router**

<span class="ooclass"> class **Yaf\_Router** </span> {

/\* Properties \*/

<span class="modifier">protected</span> `$_routes` ;

<span class="modifier">protected</span> `$_current` ;

/\* Methods \*/

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">addConfig</span> ( <span
class="methodparam"><span class="type">Yaf\_Config\_Abstract</span>
`$config`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">addRoute</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> ,
<span class="methodparam"><span class="type">Yaf\_Route\_Abstract</span>
`$route`</span> )

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getCurrentRoute</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="type">Yaf\_Route\_Interface</span> <span
class="methodname">getRoute</span> ( <span class="methodparam"><span
class="type">string</span> `$name`</span> )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">getRoutes</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">route</span> ( <span class="methodparam"><span
class="type">Yaf\_Request\_Abstract</span> `$request`</span> )

}

Properties
----------

`_routes`  
registered routes stack

`_current`  
after routing phase, this indicated the name of which route is used to
route current request. you can get this name by <span
class="methodname">Yaf\_Router::getCurrentRoute</span>.

Yaf\_Router::addConfig
======================

Add config-defined routes into Router

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Yaf\_Router::addConfig</span> ( <span
class="methodparam"><span class="type">Yaf\_Config\_Abstract</span>
`$config`</span> )

Add routes defined by configs into <span
class="classname">Yaf\_Router</span>'s route stack

### Parameters

This function has no parameters.

### Return Values

An <span class="classname">Yaf\_Config\_Abstract</span> instance, which
should contains one or more valid route configs

### Examples

**Example \#1 <span class="function">application.ini</span>example**

``` ini
;the order is very important, the prior one will be called first

;a rewrite route match request /product/*/*
routes.route_name.type="rewrite"
routes.route_name.match="/product/:name/:value"
routes.route_name.route.controller=product
routes.route_name.route.action=info

;a regex route match request /list/*/*
routes.route_name1.type="regex"
routes.route_name1.match="#^list/([^/]*)/([^/]*)#"
routes.route_name1.route.controller=Index
routes.route_name1.route.action=action
routes.route_name1.map.1=name
routes.route_name1.map.2=value

;a simple route match /**?c=controller&a=action&m=module
routes.route_name2.type="simple"
routes.route_name2.controller=c
routes.route_name2.module=m
routes.route_name2.action=a

;a simple router match /**?r=PATH_INFO
routes.route_name3.type="supervar"
routes.route_name3.varname=r

;a map route match any request to controller
routes.route_name4.type="map"
routes.route_name4.controllerPrefer=TRUE
routes.route_namer.delimiter="#!"
```

**Example \#2 <span
class="function">Yaf\_Dispatcher::autoConfig</span>example**

``` php
<?php
class Bootstrap extends Yaf_Bootstrap_Abstract{
    public function _initConfig() {
        $config = Yaf_Application::app()->getConfig();
        Yaf_Registry::set("config", $config);
    }

    public function _initRoute(Yaf_Dispatcher $dispatcher) {
        $router = $dispatcher->getRouter();
        /**
         * we can add some pre-defined routes in application.ini
         */
        $router->addConfig(Yaf_Registry::get("config")->routes);
    }
?>
```

### See Also

-   <span class="methodname">Yaf\_Router::addRoute</span>
-   <span class="classname">Yaf\_Route\_Static</span>
-   <span class="classname">Yaf\_Route\_Supervar</span>
-   <span class="classname">Yaf\_Route\_Simple</span>
-   <span class="classname">Yaf\_Route\_Regex</span>
-   <span class="classname">Yaf\_Route\_Rewrite</span>
-   <span class="classname">Yaf\_Route\_Map</span>

Yaf\_Router::addRoute
=====================

Add new Route into Router

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Yaf\_Router::addRoute</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> ,
<span class="methodparam"><span class="type">Yaf\_Route\_Abstract</span>
`$route`</span> )

defaultly, Yaf\_Router using a <span
class="classname">Yaf\_Route\_Static</span> as its defualt route. you
can add new routes into router's route stack by calling this method.

the newer route will be called before the older(route stack), and if the
newer router return **`TRUE`**, the router process will be end.
otherwise, the older one will be called.

### Parameters

This function has no parameters.

### Return Values

### Examples

**Example \#1 <span
class="function">Yaf\_Dispatcher::autoRender</span>example**

``` php
<?php
class Bootstrap extends Yaf_Bootstrap_Abstract{
    public function _initConfig() {
        $config = Yaf_Application::app()->getConfig();
        Yaf_Registry::set("config", $config);
    }

    public function _initRoute(Yaf_Dispatcher $dispatcher) {
        $router = $dispatcher->getRouter();
        /**
         * we can add some pre-defined routes in application.ini
         */
        $router->addConfig(Yaf_Registry::get("config")->routes);
        /**
         * add a Rewrite route, then for a request uri: 
         * http://***/product/list/22/foo
         * will be matched by this route, and result:
         *
         *  [module] => 
         *  [controller] => product
         *  [action] => info
         *  [method] => GET
         *  [params:protected] => Array
         *      (
         *          [id] => 22
         *          [name] => foo
         *      )
         * 
         */
        $route  = new Yaf_Route_Rewrite(
            "/product/list/:id/:name",
            array(
                "controller" => "product",
                "action"     => "info",
            )
        ); 
        
        $router->addRoute('dummy', $route);
    }
?>
```

### See Also

-   <span class="methodname">Yaf\_Router::addConfig</span>
-   <span class="classname">Yaf\_Route\_Static</span>
-   <span class="classname">Yaf\_Route\_Supervar</span>
-   <span class="classname">Yaf\_Route\_Simple</span>
-   <span class="classname">Yaf\_Route\_Regex</span>
-   <span class="classname">Yaf\_Route\_Rewrite</span>
-   <span class="classname">Yaf\_Route\_Map</span>

Yaf\_Router::\_\_construct
==========================

Yaf\_Router constructor

### Description

<span class="modifier">public</span> <span
class="methodname">Yaf\_Router::\_\_construct</span> ( <span
class="methodparam">void</span> )

### Parameters

This function has no parameters.

### Return Values

Yaf\_Router::getCurrentRoute
============================

Get the effective route name

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">Yaf\_Router::getCurrentRoute</span> ( <span
class="methodparam">void</span> )

Get the name of the route which is effective in the route process.

> **Note**:
>
> You should call this method after the route process finished, since
> before that, this method will always return **`NULL`**.

### Parameters

This function has no parameters.

### Return Values

String, the name of the effective route.

### Examples

**Example \#1 Register some routes in Bootstrap**

``` php
<?php
class Bootstrap extends Yaf_Bootstrap_Abstract{
    public function _initConfig() {
        $config = Yaf_Application::app()->getConfig();
        Yaf_Registry::set("config", $config);
    }

    public function _initRoute(Yaf_Dispatcher $dispatcher) {
        $router = $dispatcher->getRouter();
        $rewrite_route  = new Yaf_Route_Rewrite(
            "/product/list/:page",
            array(
                "controller" => "product",
                "action"     => "list",
            )
        ); 

        $regex_route  = new Yaf_Route_Rewrite(
            "#^/product/info/(\d+)",
            array(
                "controller" => "product",
                "action"     => "info",
            )
        ); 
        
        $router->addRoute('rewrite', $rewrite_route)->addRoute('regex', $regex_route);
    } 

    /**
     * register plugin 
     */
    public function __initPlugins(Yaf_Dispatcher $dispatcher) {
        $dispatcher->registerPlugin(new DummyPlugin());
    }
?>
```

**Example \#2 plugin Dummy.php (under
<a href="/yaf/appconfig.html#" class="link">application.directory</a>/plugins)**

``` php
<?php
class DummyPlugin extends Yaf_Plugin_Abstract {

    public function routerShutdown(Yaf_Request_Abstract $request, Yaf_Response_Abstract $response) {
         var_dump(Yaf_Dispatcher::getInstance()->getRouter()->getCurrentRoute());
    }
?>
?>
```

The above example will output something similar to:

    /* for http://yourdomain.com/product/list/1
     * DummyPlugin will output:
     */
    string(7) "rewrite"

    /* for http://yourdomain.com/product/info/34
     * DummyPlugin will output:
     */
    string(5) "regex"

    /* for other request URI
     * DummyPlugin will output:
     */
    string(8) "_default"

### See Also

-   <span class="classname">Yaf\_Bootstrap\_Abstract</span>
-   <span class="classname">Yaf\_Plugin\_Abstract</span>
-   <span class="methodname">Yaf\_Router::addRoute</span>

Yaf\_Router::getRoute
=====================

Retrieve a route by name

### Description

<span class="modifier">public</span> <span
class="type">Yaf\_Route\_Interface</span> <span
class="methodname">Yaf\_Router::getRoute</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> )

Retrieve a route by name, see also <span
class="methodname">Yaf\_Router::getCurrentRoute</span>

### Parameters

This function has no parameters.

### Return Values

### See Also

-   <span class="classname">Yaf\_Bootstrap\_Abstract</span>
-   <span class="classname">Yaf\_Plugin\_Abstract</span>
-   <span class="methodname">Yaf\_Router::addRoute</span>
-   <span class="methodname">Yaf\_Router::getCurrentRoute</span>

Yaf\_Router::getRoutes
======================

Retrieve registered routes

### Description

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">Yaf\_Router::getRoutes</span> ( <span
class="methodparam">void</span> )

Retrieve registered routes

### Parameters

This function has no parameters.

### Return Values

Yaf\_Router::route
==================

The route purpose

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Yaf\_Router::route</span> ( <span
class="methodparam"><span class="type">Yaf\_Request\_Abstract</span>
`$request`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

Introduction
------------

<span class="classname">Yaf\_Route\_Simple</span> will match the query
string, and find the route info.

all you need to do is tell <span
class="classname">Yaf\_Route\_Simple</span> what key in the $\_GET is
module, what key is controller, and what key is action.

<span class="methodname">Yaf\_Route\_Simple::route</span> will always
return **`TRUE`**, so it is important put <span
class="classname">Yaf\_Route\_Simple</span> in the front of the Route
stack, otherwise all the other routes will not be called.

Class synopsis
--------------

**Yaf\_Route\_Simple**

<span class="ooclass"> class **Yaf\_Route\_Simple** </span> <span
class="oointerface">implements <span
class="interfacename">Yaf\_Route\_Interface</span> </span> {

/\* Properties \*/

<span class="modifier">protected</span> `$controller` ;

<span class="modifier">protected</span> `$module` ;

<span class="modifier">protected</span> `$action` ;

/\* Methods \*/

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">assemble</span> ( <span
class="methodparam"><span class="type">array</span> `$info`</span> \[,
<span class="methodparam"><span class="type">array</span>
`$query`</span> \] )

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> ( <span
class="methodparam"><span class="type">string</span>
`$module_name`</span> , <span class="methodparam"><span
class="type">string</span> `$controller_name`</span> , <span
class="methodparam"><span class="type">string</span>
`$action_name`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">route</span> ( <span class="methodparam"><span
class="type">Yaf\_Request\_Abstract</span> `$request`</span> )

}

Properties
----------

`controller`  

`module`  

`action`  

Yaf\_Route\_Simple::assemble
============================

Assemble a url

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">Yaf\_Route\_Simple::assemble</span> ( <span
class="methodparam"><span class="type">array</span> `$info`</span> \[,
<span class="methodparam"><span class="type">array</span>
`$query`</span> \] )

Assemble a url.

### Parameters

`info`  

`query`  

### Examples

**Example \#1 <span
class="function">Yaf\_Route\_Simple::assemble</span>example**

``` php
<?php

$router = new Yaf_Router();

$route  = new Yaf_Route_Simple('m', 'c', 'a');

$router->addRoute("simple", $route);

var_dump($router->getRoute('simple')->assemble(
            array(
                ':a' => 'yafaction',
                'tkey' => 'tval',
                ':c' => 'yafcontroller',
                ':m' => 'yafmodule'
                ),
            array(
                'tkey1' => 'tval1',
                'tkey2' => 'tval2'
                )
            ));
```

The above example will output something similar to:

    string(64) "?m=yafmodule&c=yafcontroller&a=yafaction&tkey1=tval1&tkey2=tval2"

### Return Values

Yaf\_Route\_Simple::\_\_construct
=================================

Yaf\_Route\_Simple constructor

### Description

<span class="modifier">public</span> <span
class="methodname">Yaf\_Route\_Simple::\_\_construct</span> ( <span
class="methodparam"><span class="type">string</span>
`$module_name`</span> , <span class="methodparam"><span
class="type">string</span> `$controller_name`</span> , <span
class="methodparam"><span class="type">string</span>
`$action_name`</span> )

<span class="classname">Yaf\_Route\_Simple</span> will get route info
from query string. and the parameters of this constructor will used as
keys while searching for the route info in $\_GET.

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`module_name`  
The key name of the module info.

`controller_name`  
the key name of the controller info.

`action_name`  
the key name of the action info.

### Return Values

Always return **`TRUE`**.

### Examples

**Example \#1 <span
class="function">Yaf\_Route\_Simple::route</span>example**

``` php
<?php
   $route = new Yaf_Route_Simple("m", "controller", "act");
   Yaf_Router::getInstance()->addRoute("simple", $route);
?>
```

**Example \#2 <span
class="function">Yaf\_Route\_Simple::route</span>example**

``` bash
Request: http://yourdomain.com/path/?controller=a&act=b
=> module = default(index), controller = a, action = b

Request: http://yourdomain.com/path
=> module = default(index), controller = default(index), action = default(index)
```

### See Also

-   <span class="methodname">Yaf\_Route\_Supervar::route</span>
-   <span class="methodname">Yaf\_Route\_Static::route</span>
-   <span class="methodname">Yaf\_Route\_Regex::route</span>
-   <span class="methodname">Yaf\_Route\_Rewrite::route</span>
-   <span class="methodname">Yaf\_Route\_Map::route</span>

Yaf\_Route\_Simple::route
=========================

Route a request

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Yaf\_Route\_Simple::route</span> ( <span
class="methodparam"><span class="type">Yaf\_Request\_Abstract</span>
`$request`</span> )

see <span class="methodname">Yaf\_Route\_Simple::\_\_construct</span>

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`request`  

### Return Values

always be **`TRUE`**

### See Also

-   <span class="methodname">Yaf\_Route\_Supervar::route</span>
-   <span class="methodname">Yaf\_Route\_Static::route</span>
-   <span class="methodname">Yaf\_Route\_Regex::route</span>
-   <span class="methodname">Yaf\_Route\_Rewrite::route</span>
-   <span class="methodname">Yaf\_Route\_Map::route</span>

Introduction
------------

Defaultly, <span class="classname">Yaf\_Router</span> only have a <span
class="classname">Yaf\_Route\_Static</span> as its default route.

And <span class="classname">Yaf\_Route\_Static</span> is designed to
handle the 80% requirement.

please \*NOTE\* that it is unnecessary to instance a <span
class="classname">Yaf\_Route\_Static</span>, also unecesary to add it
into <span class="classname">Yaf\_Router</span>'s routes stack, since
there is always be one in <span class="classname">Yaf\_Router</span>'s
routes stack, and always be called at the last time.

Class synopsis
--------------

**Yaf\_Route\_Static**

<span class="ooclass"> class **Yaf\_Route\_Static** </span> <span
class="oointerface">implements <span
class="interfacename">Yaf\_Router</span> </span> {

/\* Methods \*/

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">assemble</span> ( <span
class="methodparam"><span class="type">array</span> `$info`</span> \[,
<span class="methodparam"><span class="type">array</span>
`$query`</span> \] )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">match</span> ( <span class="methodparam"><span
class="type">string</span> `$uri`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">route</span> ( <span class="methodparam"><span
class="type">Yaf\_Request\_Abstract</span> `$request`</span> )

}

Yaf\_Route\_Static::assemble
============================

Assemble a url

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">Yaf\_Route\_Static::assemble</span> ( <span
class="methodparam"><span class="type">array</span> `$info`</span> \[,
<span class="methodparam"><span class="type">array</span>
`$query`</span> \] )

Assemble a url.

### Parameters

`info`  

`query`  

### Examples

**Example \#1 <span
class="function">Yaf\_Route\_Static::assemble</span>example**

``` php
<?php

$router = new Yaf_Router();

$route  = new Yaf_Route_Static();

$router->addRoute("static", $route);

var_dump($router->getRoute('static')->assemble(
            array(
                ':a' => 'yafaction',
                'tkey' => 'tval',
                ':c' => 'yafcontroller',
                ':m' => 'yafmodule'
            ),
        )
);

var_dump($router->getRoute('static')->assemble(
            array(
                ':a' => 'yafaction',
                'tkey' => 'tval',
                ':c' => 'yafcontroller',
                ':m' => 'yafmodule'
            ),
            array(
                'tkey1' => 'tval1',
                'tkey2' => 'tval2'
            )
        )
);
```

The above example will output something similar to:

    string(%d) "/yafmodule/yafcontroller/yafaction"
    string(%d) "/yafmodule/yafcontroller/yafaction?tkey1=tval1&tkey2=tval2"

### Return Values

Yaf\_Route\_Static::match
=========================

The match purpose

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Route\_Static::match</span> ( <span
class="methodparam"><span class="type">string</span> `$uri`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`uri`  

### Return Values

Yaf\_Route\_Static::route
=========================

Route a request

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Yaf\_Route\_Static::route</span> ( <span
class="methodparam"><span class="type">Yaf\_Request\_Abstract</span>
`$request`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`request`  

### Return Values

always be **`TRUE`**

### Examples

**Example \#1 <span
class="function">Yaf\_Route\_Static::route</span>example**

``` shell
// assuming there is only one module defined:Index
Request: http://yourdomain.com/a/b
=> module = index, controller=a, action=b

//assuming ap.action_prefer = On
Request: http://yourdomain.com/b
=> module = default(index), controller = default(index), action = b

//assuming ap.action_prefer = Off
Request: http://yourdomain.com/b
=> module = default(index), controller = b, action = default(index)


Request: http://yourdomain.com/a/b/foo/bar/test/a/id/4
=> module = default(index), controller = a, action = b, request parameters: foo = bar, test = a, id = 4
```

### See Also

-   <span class="methodname">Yaf\_Route\_Supervar::route</span>
-   <span class="methodname">Yaf\_Route\_Simple::route</span>
-   <span class="methodname">Yaf\_Route\_Regex::route</span>
-   <span class="methodname">Yaf\_Route\_Rewrite::route</span>
-   <span class="methodname">Yaf\_Route\_Map::route</span>

Introduction
------------

Class synopsis
--------------

**Yaf\_Route\_Supervar**

<span class="ooclass"> class **Yaf\_Route\_Supervar** </span> <span
class="oointerface">implements <span
class="interfacename">Yaf\_Route\_Interface</span> </span> {

/\* Properties \*/

<span class="modifier">protected</span> `$_var_name` ;

/\* Methods \*/

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">assemble</span> ( <span
class="methodparam"><span class="type">array</span> `$info`</span> \[,
<span class="methodparam"><span class="type">array</span>
`$query`</span> \] )

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> ( <span
class="methodparam"><span class="type">string</span>
`$supervar_name`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">route</span> ( <span class="methodparam"><span
class="type">Yaf\_Request\_Abstract</span> `$request`</span> )

}

Properties
----------

`_var_name`  

Yaf\_Route\_Supervar::assemble
==============================

Assemble a url

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">Yaf\_Route\_Supervar::assemble</span> ( <span
class="methodparam"><span class="type">array</span> `$info`</span> \[,
<span class="methodparam"><span class="type">array</span>
`$query`</span> \] )

Assemble a url.

### Parameters

`info`  

`query`  

### Examples

**Example \#1 <span
class="function">Yaf\_Route\_Supervar::assemble</span>example**

``` php
<?php

$router = new Yaf_Router();

$route  = new Yaf_Route_Supervar('r');

$router->addRoute("supervar", $route);

var_dump($router->getRoute('supervar')->assemble(
        array(
              ':a' => 'yafaction',
              'tkey' => 'tval',
              ':c' => 'yafcontroller',
              ':m' => 'yafmodule'
        ),
        array(
              'tkey1' => 'tval1',
              'tkey2' => 'tval2'
        )
));

try {
var_dump($router->getRoute('supervar')->assemble(
        array(
              ':a' => 'yafaction',
              'tkey' => 'tval',
              ':m' => 'yafmodule'
        ),
        array(
              'tkey1' => 'tval1',
              'tkey2' => 'tval2',
              1 => array(),
        )
));
} catch (Exception $e) {
    var_dump($e->getMessage());
}
```

The above example will output something similar to:

    string(%d) "?r=/yafmodule/yafcontroller/yafaction&tkey1=tval1&tkey2=tval2"
    string(%d) "You need to specify the controller by ':c'"

### Return Values

Yaf\_Route\_Supervar::\_\_construct
===================================

The \_\_construct purpose

### Description

<span class="modifier">public</span> <span
class="methodname">Yaf\_Route\_Supervar::\_\_construct</span> ( <span
class="methodparam"><span class="type">string</span>
`$supervar_name`</span> )

<span class="classname">Yaf\_Route\_Supervar</span> is similar with
<span class="classname">Yaf\_Route\_Static</span>, the difference is
<span class="classname">Yaf\_Route\_Supervar</span> will look for path
info in query string, and the parameter `supervar_name` is the key.

### Parameters

`supervar_name`  
The name of key.

### Return Values

### Examples

**Example \#1 <span
class="function">Yaf\_Route\_Supervar</span>example**

``` php
<?php
   /**
    * Add a supervar route to Yaf_Router route stack
    */
    Yaf_Dispatcher::getInstance()->getRouter()->addRoute("name",
        new Yaf_Route_Supervar("r"));
    );
?>
```

The above example will output something similar to:

    /** for request: http://yourdomain.com/xx/oo/?r=/ctr/act/var/value
      * will result in following:
      */
      array (
        "module"   => index(default),
        "controller" => ctr,
        "action"     => act,
        "params"     => array(
              "var" => value,
         )
      )

### See Also

-   <span class="methodname">Yaf\_Router::addRoute</span>
-   <span class="methodname">Yaf\_Router::addConfig</span>
-   <span class="classname">Yaf\_Route\_Static</span>
-   <span class="classname">Yaf\_Route\_Regex</span>
-   <span class="classname">Yaf\_Route\_Simple</span>
-   <span class="classname">Yaf\_Route\_Rewrite</span>
-   <span class="classname">Yaf\_Route\_Map</span>

Yaf\_Route\_Supervar::route
===========================

The route purpose

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Yaf\_Route\_Supervar::route</span> ( <span
class="methodparam"><span class="type">Yaf\_Request\_Abstract</span>
`$request`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`request`  

### Return Values

If there is a key(which was defined in <span
class="methodname">Yaf\_Route\_Supervar::\_\_construct</span>) in
$\_GET, return **`TRUE`**. otherwise return **`FALSE`**.

Introduction
------------

Class synopsis
--------------

**Yaf\_Session**

<span class="ooclass"> class **Yaf\_Session** </span> <span
class="oointerface">implements <span
class="interfacename">Iterator</span> </span> <span
class="oointerface">, <span class="interfacename">ArrayAccess</span>
</span> <span class="oointerface">, <span
class="interfacename">Countable</span> </span> {

/\* Properties \*/

<span class="modifier">protected</span> <span
class="modifier">static</span> `$_instance` ;

<span class="modifier">protected</span> `$_session` ;

<span class="modifier">protected</span> `$_started` ;

/\* Methods \*/

<span class="modifier">private</span> <span
class="methodname">\_\_construct</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">count</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">current</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">del</span> ( <span class="methodparam"><span
class="type">string</span> `$name`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">\_\_get</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> )

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">void</span> <span
class="methodname">getInstance</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">has</span> ( <span class="methodparam"><span
class="type">string</span> `$name`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">\_\_isset</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">key</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">next</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">offsetExists</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">offsetGet</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">offsetSet</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> ,
<span class="methodparam"><span class="type">string</span>
`$value`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">offsetUnset</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">rewind</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">\_\_set</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> ,
<span class="methodparam"><span class="type">string</span>
`$value`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">start</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">\_\_unset</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">valid</span> ( <span
class="methodparam">void</span> )

}

Properties
----------

`_instance`  

`_session`  

`_started`  

Yaf\_Session::\_\_construct
===========================

Constructor of Yaf\_Session

### Description

<span class="modifier">private</span> <span
class="methodname">Yaf\_Session::\_\_construct</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

Yaf\_Session::count
===================

The count purpose

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Session::count</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

Yaf\_Session::current
=====================

The current purpose

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Session::current</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

Yaf\_Session::del
=================

The del purpose

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Session::del</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`name`  

### Return Values

Yaf\_Session::\_\_get
=====================

The \_\_get purpose

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Session::\_\_get</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`name`  

### Return Values

Yaf\_Session::getInstance
=========================

The getInstance purpose

### Description

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">void</span> <span
class="methodname">Yaf\_Session::getInstance</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

Yaf\_Session::has
=================

The has purpose

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Session::has</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`name`  

### Return Values

Yaf\_Session::\_\_isset
=======================

The \_\_isset purpose

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Session::\_\_isset</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`name`  

### Return Values

Yaf\_Session::key
=================

The key purpose

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Session::key</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

Yaf\_Session::next
==================

The next purpose

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Session::next</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

Yaf\_Session::offsetExists
==========================

The offsetExists purpose

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Session::offsetExists</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`name`  

### Return Values

Yaf\_Session::offsetGet
=======================

The offsetGet purpose

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Session::offsetGet</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`name`  

### Return Values

Yaf\_Session::offsetSet
=======================

The offsetSet purpose

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Session::offsetSet</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> ,
<span class="methodparam"><span class="type">string</span>
`$value`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`name`  

`value`  

### Return Values

Yaf\_Session::offsetUnset
=========================

The offsetUnset purpose

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Session::offsetUnset</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`name`  

### Return Values

Yaf\_Session::rewind
====================

The rewind purpose

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Session::rewind</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

Yaf\_Session::\_\_set
=====================

The \_\_set purpose

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Session::\_\_set</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> ,
<span class="methodparam"><span class="type">string</span>
`$value`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`name`  

`value`  

### Return Values

Yaf\_Session::start
===================

The start purpose

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Session::start</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

Yaf\_Session::\_\_unset
=======================

The \_\_unset purpose

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Session::\_\_unset</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`name`  

### Return Values

Yaf\_Session::valid
===================

The valid purpose

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Session::valid</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

Introduction
------------

Class synopsis
--------------

**Yaf\_Exception**

<span class="ooclass"> class **Yaf\_Exception** </span> <span
class="ooclass"> <span class="modifier">extends</span> **Exception**
</span> {

/\* Inherited properties \*/

<span class="modifier">protected</span> <span class="type">string</span>
`$message` ;

<span class="modifier">protected</span> <span class="type">int</span>
`$code` ;

<span class="modifier">protected</span> <span class="type">string</span>
`$file` ;

<span class="modifier">protected</span> <span class="type">int</span>
`$line` ;

/\* Methods \*/

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">getPrevious</span> ( <span
class="methodparam">void</span> )

/\* Inherited methods \*/

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">Exception::getMessage</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">Throwable</span> <span
class="methodname">Exception::getPrevious</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">mixed</span> <span
class="methodname">Exception::getCode</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">Exception::getFile</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">int</span> <span
class="methodname">Exception::getLine</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">array</span> <span
class="methodname">Exception::getTrace</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">Exception::getTraceAsString</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">Exception::\_\_toString</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span
class="modifier">private</span> <span class="type">void</span> <span
class="methodname">Exception::\_\_clone</span> ( <span
class="methodparam">void</span> )

}

Yaf\_Exception::\_\_construct
=============================

The \_\_construct purpose

### Description

<span class="modifier">public</span> <span
class="methodname">Yaf\_Exception::\_\_construct</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

Yaf\_Exception::getPrevious
===========================

The getPrevious purpose

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Exception::getPrevious</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

Introduction
------------

Class synopsis
--------------

**Yaf\_Exception\_TypeError**

<span class="ooclass"> class **Yaf\_Exception\_TypeError** </span> <span
class="ooclass"> <span class="modifier">extends</span>
**Yaf\_Exception** </span> {

/\* Properties \*/

/\* Methods \*/

/\* Inherited methods \*/

<span class="modifier">public</span> <span
class="methodname">Yaf\_Exception::\_\_construct</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Exception::getPrevious</span> ( <span
class="methodparam">void</span> )

}

Introduction
------------

Class synopsis
--------------

**Yaf\_Exception\_StartupError**

<span class="ooclass"> class **Yaf\_Exception\_StartupError** </span>
<span class="ooclass"> <span class="modifier">extends</span>
**Yaf\_Exception** </span> {

/\* Properties \*/

/\* Methods \*/

/\* Inherited methods \*/

<span class="modifier">public</span> <span
class="methodname">Yaf\_Exception::\_\_construct</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Exception::getPrevious</span> ( <span
class="methodparam">void</span> )

}

Introduction
------------

Class synopsis
--------------

**Yaf\_Exception\_DispatchFailed**

<span class="ooclass"> class **Yaf\_Exception\_DispatchFailed** </span>
<span class="ooclass"> <span class="modifier">extends</span>
**Yaf\_Exception** </span> {

/\* Properties \*/

/\* Methods \*/

/\* Inherited methods \*/

<span class="modifier">public</span> <span
class="methodname">Yaf\_Exception::\_\_construct</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Exception::getPrevious</span> ( <span
class="methodparam">void</span> )

}

Introduction
------------

Class synopsis
--------------

**Yaf\_Exception\_RouterFailed**

<span class="ooclass"> class **Yaf\_Exception\_RouterFailed** </span>
<span class="ooclass"> <span class="modifier">extends</span>
**Yaf\_Exception** </span> {

/\* Properties \*/

/\* Methods \*/

/\* Inherited methods \*/

<span class="modifier">public</span> <span
class="methodname">Yaf\_Exception::\_\_construct</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Exception::getPrevious</span> ( <span
class="methodparam">void</span> )

}

Introduction
------------

Class synopsis
--------------

**Yaf\_Exception\_LoadFailed**

<span class="ooclass"> class **Yaf\_Exception\_LoadFailed** </span>
<span class="ooclass"> <span class="modifier">extends</span>
**Yaf\_Exception** </span> {

/\* Properties \*/

/\* Methods \*/

/\* Inherited methods \*/

<span class="modifier">public</span> <span
class="methodname">Yaf\_Exception::\_\_construct</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Exception::getPrevious</span> ( <span
class="methodparam">void</span> )

}

Introduction
------------

Class synopsis
--------------

**Yaf\_Exception\_LoadFailed\_Module**

<span class="ooclass"> class **Yaf\_Exception\_LoadFailed\_Module**
</span> <span class="ooclass"> <span class="modifier">extends</span>
**Yaf\_Exception\_LoadFailed** </span> {

/\* Properties \*/

/\* Methods \*/

/\* Inherited methods \*/

<span class="modifier">public</span> <span
class="methodname">Yaf\_Exception::\_\_construct</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Exception::getPrevious</span> ( <span
class="methodparam">void</span> )

}

Introduction
------------

Class synopsis
--------------

**Yaf\_Exception\_LoadFailed\_Controller**

<span class="ooclass"> class **Yaf\_Exception\_LoadFailed\_Controller**
</span> <span class="ooclass"> <span class="modifier">extends</span>
**Yaf\_Exception\_LoadFailed** </span> {

/\* Properties \*/

/\* Methods \*/

/\* Inherited methods \*/

<span class="modifier">public</span> <span
class="methodname">Yaf\_Exception::\_\_construct</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Exception::getPrevious</span> ( <span
class="methodparam">void</span> )

}

Introduction
------------

Class synopsis
--------------

**Yaf\_Exception\_LoadFailed\_Action**

<span class="ooclass"> class **Yaf\_Exception\_LoadFailed\_Action**
</span> <span class="ooclass"> <span class="modifier">extends</span>
**Yaf\_Exception\_LoadFailed** </span> {

/\* Properties \*/

/\* Methods \*/

/\* Inherited methods \*/

<span class="modifier">public</span> <span
class="methodname">Yaf\_Exception::\_\_construct</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Exception::getPrevious</span> ( <span
class="methodparam">void</span> )

}

Introduction
------------

Class synopsis
--------------

**Yaf\_Exception\_LoadFailed\_View**

<span class="ooclass"> class **Yaf\_Exception\_LoadFailed\_View**
</span> <span class="ooclass"> <span class="modifier">extends</span>
**Yaf\_Exception\_LoadFailed** </span> {

/\* Properties \*/

/\* Methods \*/

/\* Inherited methods \*/

<span class="modifier">public</span> <span
class="methodname">Yaf\_Exception::\_\_construct</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yaf\_Exception::getPrevious</span> ( <span
class="methodparam">void</span> )

}
