Reflection
==========

**Table of Contents**

-   [Introduction](/intro/reflection.html)
-   [Installing/Configuring](/reflection/setup.html)
    -   [Requirements](/reflection/setup.html#Requirements)
    -   [Installation](/reflection/setup.html#Installation)
    -   [Runtime
        Configuration](/reflection/setup.html#Runtime%20Configuration)
    -   [Resource Types](/reflection/setup.html#Resource%20Types)
-   [Predefined Constants](/reflection/constants.html)
-   [Examples](/reflection/examples.html)
-   [Extending](/reflection/extending.html)
-   [Reflection](/class/reflection.html) — The Reflection class
    -   [Reflection::export](/class/reflection.html#Reflection::export)
        — Exports
    -   [Reflection::getModifierNames](/class/reflection.html#Reflection::getModifierNames)
        — Gets modifier names
-   [ReflectionClass](/class/reflectionclass.html) — The ReflectionClass
    class
    -   [ReflectionClass::\_\_construct](/class/reflectionclass.html#ReflectionClass::__construct)
        — Constructs a ReflectionClass
    -   [ReflectionClass::export](/class/reflectionclass.html#ReflectionClass::export)
        — Exports a class
    -   [ReflectionClass::getConstant](/class/reflectionclass.html#ReflectionClass::getConstant)
        — Gets defined constant
    -   [ReflectionClass::getConstants](/class/reflectionclass.html#ReflectionClass::getConstants)
        — Gets constants
    -   [ReflectionClass::getConstructor](/class/reflectionclass.html#ReflectionClass::getConstructor)
        — Gets the constructor of the class
    -   [ReflectionClass::getDefaultProperties](/class/reflectionclass.html#ReflectionClass::getDefaultProperties)
        — Gets default properties
    -   [ReflectionClass::getDocComment](/class/reflectionclass.html#ReflectionClass::getDocComment)
        — Gets doc comments
    -   [ReflectionClass::getEndLine](/class/reflectionclass.html#ReflectionClass::getEndLine)
        — Gets end line
    -   [ReflectionClass::getExtension](/class/reflectionclass.html#ReflectionClass::getExtension)
        — Gets a ReflectionExtension object for the extension which
        defined the class
    -   [ReflectionClass::getExtensionName](/class/reflectionclass.html#ReflectionClass::getExtensionName)
        — Gets the name of the extension which defined the class
    -   [ReflectionClass::getFileName](/class/reflectionclass.html#ReflectionClass::getFileName)
        — Gets the filename of the file in which the class has been
        defined
    -   [ReflectionClass::getInterfaceNames](/class/reflectionclass.html#ReflectionClass::getInterfaceNames)
        — Gets the interface names
    -   [ReflectionClass::getInterfaces](/class/reflectionclass.html#ReflectionClass::getInterfaces)
        — Gets the interfaces
    -   [ReflectionClass::getMethod](/class/reflectionclass.html#ReflectionClass::getMethod)
        — Gets a ReflectionMethod for a class method
    -   [ReflectionClass::getMethods](/class/reflectionclass.html#ReflectionClass::getMethods)
        — Gets an array of methods
    -   [ReflectionClass::getModifiers](/class/reflectionclass.html#ReflectionClass::getModifiers)
        — Gets the class modifiers
    -   [ReflectionClass::getName](/class/reflectionclass.html#ReflectionClass::getName)
        — Gets class name
    -   [ReflectionClass::getNamespaceName](/class/reflectionclass.html#ReflectionClass::getNamespaceName)
        — Gets namespace name
    -   [ReflectionClass::getParentClass](/class/reflectionclass.html#ReflectionClass::getParentClass)
        — Gets parent class
    -   [ReflectionClass::getProperties](/class/reflectionclass.html#ReflectionClass::getProperties)
        — Gets properties
    -   [ReflectionClass::getProperty](/class/reflectionclass.html#ReflectionClass::getProperty)
        — Gets a ReflectionProperty for a class's property
    -   [ReflectionClass::getReflectionConstant](/class/reflectionclass.html#ReflectionClass::getReflectionConstant)
        — Gets a ReflectionClassConstant for a class's constant
    -   [ReflectionClass::getReflectionConstants](/class/reflectionclass.html#ReflectionClass::getReflectionConstants)
        — Gets class constants
    -   [ReflectionClass::getShortName](/class/reflectionclass.html#ReflectionClass::getShortName)
        — Gets short name
    -   [ReflectionClass::getStartLine](/class/reflectionclass.html#ReflectionClass::getStartLine)
        — Gets starting line number
    -   [ReflectionClass::getStaticProperties](/class/reflectionclass.html#ReflectionClass::getStaticProperties)
        — Gets static properties
    -   [ReflectionClass::getStaticPropertyValue](/class/reflectionclass.html#ReflectionClass::getStaticPropertyValue)
        — Gets static property value
    -   [ReflectionClass::getTraitAliases](/class/reflectionclass.html#ReflectionClass::getTraitAliases)
        — Returns an array of trait aliases
    -   [ReflectionClass::getTraitNames](/class/reflectionclass.html#ReflectionClass::getTraitNames)
        — Returns an array of names of traits used by this class
    -   [ReflectionClass::getTraits](/class/reflectionclass.html#ReflectionClass::getTraits)
        — Returns an array of traits used by this class
    -   [ReflectionClass::hasConstant](/class/reflectionclass.html#ReflectionClass::hasConstant)
        — Checks if constant is defined
    -   [ReflectionClass::hasMethod](/class/reflectionclass.html#ReflectionClass::hasMethod)
        — Checks if method is defined
    -   [ReflectionClass::hasProperty](/class/reflectionclass.html#ReflectionClass::hasProperty)
        — Checks if property is defined
    -   [ReflectionClass::implementsInterface](/class/reflectionclass.html#ReflectionClass::implementsInterface)
        — Implements interface
    -   [ReflectionClass::inNamespace](/class/reflectionclass.html#ReflectionClass::inNamespace)
        — Checks if in namespace
    -   [ReflectionClass::isAbstract](/class/reflectionclass.html#ReflectionClass::isAbstract)
        — Checks if class is abstract
    -   [ReflectionClass::isAnonymous](/class/reflectionclass.html#ReflectionClass::isAnonymous)
        — Checks if class is anonymous
    -   [ReflectionClass::isCloneable](/class/reflectionclass.html#ReflectionClass::isCloneable)
        — Returns whether this class is cloneable
    -   [ReflectionClass::isFinal](/class/reflectionclass.html#ReflectionClass::isFinal)
        — Checks if class is final
    -   [ReflectionClass::isInstance](/class/reflectionclass.html#ReflectionClass::isInstance)
        — Checks class for instance
    -   [ReflectionClass::isInstantiable](/class/reflectionclass.html#ReflectionClass::isInstantiable)
        — Checks if the class is instantiable
    -   [ReflectionClass::isInterface](/class/reflectionclass.html#ReflectionClass::isInterface)
        — Checks if the class is an interface
    -   [ReflectionClass::isInternal](/class/reflectionclass.html#ReflectionClass::isInternal)
        — Checks if class is defined internally by an extension, or the
        core
    -   [ReflectionClass::isIterable](/class/reflectionclass.html#ReflectionClass::isIterable)
        — Check whether this class is iterable
    -   [ReflectionClass::isIterateable](/class/reflectionclass.html#ReflectionClass::isIterateable)
        — Alias of ReflectionClass::isIterable
    -   [ReflectionClass::isSubclassOf](/class/reflectionclass.html#ReflectionClass::isSubclassOf)
        — Checks if a subclass
    -   [ReflectionClass::isTrait](/class/reflectionclass.html#ReflectionClass::isTrait)
        — Returns whether this is a trait
    -   [ReflectionClass::isUserDefined](/class/reflectionclass.html#ReflectionClass::isUserDefined)
        — Checks if user defined
    -   [ReflectionClass::newInstance](/class/reflectionclass.html#ReflectionClass::newInstance)
        — Creates a new class instance from given arguments
    -   [ReflectionClass::newInstanceArgs](/class/reflectionclass.html#ReflectionClass::newInstanceArgs)
        — Creates a new class instance from given arguments
    -   [ReflectionClass::newInstanceWithoutConstructor](/class/reflectionclass.html#ReflectionClass::newInstanceWithoutConstructor)
        — Creates a new class instance without invoking the constructor
    -   [ReflectionClass::setStaticPropertyValue](/class/reflectionclass.html#ReflectionClass::setStaticPropertyValue)
        — Sets static property value
    -   [ReflectionClass::\_\_toString](/class/reflectionclass.html#ReflectionClass::__toString)
        — Returns the string representation of the ReflectionClass
        object
-   [ReflectionClassConstant](/class/reflectionclassconstant.html) — The
    ReflectionClassConstant class
    -   [ReflectionClassConstant::\_\_construct](/class/reflectionclassconstant.html#ReflectionClassConstant::__construct)
        — Constructs a ReflectionClassConstant
    -   [ReflectionClassConstant::export](/class/reflectionclassconstant.html#ReflectionClassConstant::export)
        — Export
    -   [ReflectionClassConstant::getDeclaringClass](/class/reflectionclassconstant.html#ReflectionClassConstant::getDeclaringClass)
        — Gets declaring class
    -   [ReflectionClassConstant::getDocComment](/class/reflectionclassconstant.html#ReflectionClassConstant::getDocComment)
        — Gets doc comments
    -   [ReflectionClassConstant::getModifiers](/class/reflectionclassconstant.html#ReflectionClassConstant::getModifiers)
        — Gets the class constant modifiers
    -   [ReflectionClassConstant::getName](/class/reflectionclassconstant.html#ReflectionClassConstant::getName)
        — Get name of the constant
    -   [ReflectionClassConstant::getValue](/class/reflectionclassconstant.html#ReflectionClassConstant::getValue)
        — Gets value
    -   [ReflectionClassConstant::isPrivate](/class/reflectionclassconstant.html#ReflectionClassConstant::isPrivate)
        — Checks if class constant is private
    -   [ReflectionClassConstant::isProtected](/class/reflectionclassconstant.html#ReflectionClassConstant::isProtected)
        — Checks if class constant is protected
    -   [ReflectionClassConstant::isPublic](/class/reflectionclassconstant.html#ReflectionClassConstant::isPublic)
        — Checks if class constant is public
    -   [ReflectionClassConstant::\_\_toString](/class/reflectionclassconstant.html#ReflectionClassConstant::__toString)
        — Returns the string representation of the
        ReflectionClassConstant object
-   [ReflectionZendExtension](/class/reflectionzendextension.html) — The
    ReflectionZendExtension class
    -   [ReflectionZendExtension::\_\_clone](/class/reflectionzendextension.html#ReflectionZendExtension::__clone)
        — Clone handler
    -   [ReflectionZendExtension::\_\_construct](/class/reflectionzendextension.html#ReflectionZendExtension::__construct)
        — Constructor
    -   [ReflectionZendExtension::export](/class/reflectionzendextension.html#ReflectionZendExtension::export)
        — Export
    -   [ReflectionZendExtension::getAuthor](/class/reflectionzendextension.html#ReflectionZendExtension::getAuthor)
        — Gets author
    -   [ReflectionZendExtension::getCopyright](/class/reflectionzendextension.html#ReflectionZendExtension::getCopyright)
        — Gets copyright
    -   [ReflectionZendExtension::getName](/class/reflectionzendextension.html#ReflectionZendExtension::getName)
        — Gets name
    -   [ReflectionZendExtension::getURL](/class/reflectionzendextension.html#ReflectionZendExtension::getURL)
        — Gets URL
    -   [ReflectionZendExtension::getVersion](/class/reflectionzendextension.html#ReflectionZendExtension::getVersion)
        — Gets version
    -   [ReflectionZendExtension::\_\_toString](/class/reflectionzendextension.html#ReflectionZendExtension::__toString)
        — To string handler
-   [ReflectionExtension](/class/reflectionextension.html) — The
    ReflectionExtension class
    -   [ReflectionExtension::\_\_clone](/class/reflectionextension.html#ReflectionExtension::__clone)
        — Clones
    -   [ReflectionExtension::\_\_construct](/class/reflectionextension.html#ReflectionExtension::__construct)
        — Constructs a ReflectionExtension
    -   [ReflectionExtension::export](/class/reflectionextension.html#ReflectionExtension::export)
        — Export
    -   [ReflectionExtension::getClasses](/class/reflectionextension.html#ReflectionExtension::getClasses)
        — Gets classes
    -   [ReflectionExtension::getClassNames](/class/reflectionextension.html#ReflectionExtension::getClassNames)
        — Gets class names
    -   [ReflectionExtension::getConstants](/class/reflectionextension.html#ReflectionExtension::getConstants)
        — Gets constants
    -   [ReflectionExtension::getDependencies](/class/reflectionextension.html#ReflectionExtension::getDependencies)
        — Gets dependencies
    -   [ReflectionExtension::getFunctions](/class/reflectionextension.html#ReflectionExtension::getFunctions)
        — Gets extension functions
    -   [ReflectionExtension::getINIEntries](/class/reflectionextension.html#ReflectionExtension::getINIEntries)
        — Gets extension ini entries
    -   [ReflectionExtension::getName](/class/reflectionextension.html#ReflectionExtension::getName)
        — Gets extension name
    -   [ReflectionExtension::getVersion](/class/reflectionextension.html#ReflectionExtension::getVersion)
        — Gets extension version
    -   [ReflectionExtension::info](/class/reflectionextension.html#ReflectionExtension::info)
        — Print extension info
    -   [ReflectionExtension::isPersistent](/class/reflectionextension.html#ReflectionExtension::isPersistent)
        — Returns whether this extension is persistent
    -   [ReflectionExtension::isTemporary](/class/reflectionextension.html#ReflectionExtension::isTemporary)
        — Returns whether this extension is temporary
    -   [ReflectionExtension::\_\_toString](/class/reflectionextension.html#ReflectionExtension::__toString)
        — To string
-   [ReflectionFunction](/class/reflectionfunction.html) — The
    ReflectionFunction class
    -   [ReflectionFunction::\_\_construct](/class/reflectionfunction.html#ReflectionFunction::__construct)
        — Constructs a ReflectionFunction object
    -   [ReflectionFunction::export](/class/reflectionfunction.html#ReflectionFunction::export)
        — Exports function
    -   [ReflectionFunction::getClosure](/class/reflectionfunction.html#ReflectionFunction::getClosure)
        — Returns a dynamically created closure for the function
    -   [ReflectionFunction::invoke](/class/reflectionfunction.html#ReflectionFunction::invoke)
        — Invokes function
    -   [ReflectionFunction::invokeArgs](/class/reflectionfunction.html#ReflectionFunction::invokeArgs)
        — Invokes function args
    -   [ReflectionFunction::isDisabled](/class/reflectionfunction.html#ReflectionFunction::isDisabled)
        — Checks if function is disabled
    -   [ReflectionFunction::\_\_toString](/class/reflectionfunction.html#ReflectionFunction::__toString)
        — To string
-   [ReflectionFunctionAbstract](/class/reflectionfunctionabstract.html)
    — The ReflectionFunctionAbstract class
    -   [ReflectionFunctionAbstract::\_\_clone](/class/reflectionfunctionabstract.html#ReflectionFunctionAbstract::__clone)
        — Clones function
    -   [ReflectionFunctionAbstract::getClosureScopeClass](/class/reflectionfunctionabstract.html#ReflectionFunctionAbstract::getClosureScopeClass)
        — Returns the scope associated to the closure
    -   [ReflectionFunctionAbstract::getClosureThis](/class/reflectionfunctionabstract.html#ReflectionFunctionAbstract::getClosureThis)
        — Returns this pointer bound to closure
    -   [ReflectionFunctionAbstract::getDocComment](/class/reflectionfunctionabstract.html#ReflectionFunctionAbstract::getDocComment)
        — Gets doc comment
    -   [ReflectionFunctionAbstract::getEndLine](/class/reflectionfunctionabstract.html#ReflectionFunctionAbstract::getEndLine)
        — Gets end line number
    -   [ReflectionFunctionAbstract::getExtension](/class/reflectionfunctionabstract.html#ReflectionFunctionAbstract::getExtension)
        — Gets extension info
    -   [ReflectionFunctionAbstract::getExtensionName](/class/reflectionfunctionabstract.html#ReflectionFunctionAbstract::getExtensionName)
        — Gets extension name
    -   [ReflectionFunctionAbstract::getFileName](/class/reflectionfunctionabstract.html#ReflectionFunctionAbstract::getFileName)
        — Gets file name
    -   [ReflectionFunctionAbstract::getName](/class/reflectionfunctionabstract.html#ReflectionFunctionAbstract::getName)
        — Gets function name
    -   [ReflectionFunctionAbstract::getNamespaceName](/class/reflectionfunctionabstract.html#ReflectionFunctionAbstract::getNamespaceName)
        — Gets namespace name
    -   [ReflectionFunctionAbstract::getNumberOfParameters](/class/reflectionfunctionabstract.html#ReflectionFunctionAbstract::getNumberOfParameters)
        — Gets number of parameters
    -   [ReflectionFunctionAbstract::getNumberOfRequiredParameters](/class/reflectionfunctionabstract.html#ReflectionFunctionAbstract::getNumberOfRequiredParameters)
        — Gets number of required parameters
    -   [ReflectionFunctionAbstract::getParameters](/class/reflectionfunctionabstract.html#ReflectionFunctionAbstract::getParameters)
        — Gets parameters
    -   [ReflectionFunctionAbstract::getReturnType](/class/reflectionfunctionabstract.html#ReflectionFunctionAbstract::getReturnType)
        — Gets the specified return type of a function
    -   [ReflectionFunctionAbstract::getShortName](/class/reflectionfunctionabstract.html#ReflectionFunctionAbstract::getShortName)
        — Gets function short name
    -   [ReflectionFunctionAbstract::getStartLine](/class/reflectionfunctionabstract.html#ReflectionFunctionAbstract::getStartLine)
        — Gets starting line number
    -   [ReflectionFunctionAbstract::getStaticVariables](/class/reflectionfunctionabstract.html#ReflectionFunctionAbstract::getStaticVariables)
        — Gets static variables
    -   [ReflectionFunctionAbstract::hasReturnType](/class/reflectionfunctionabstract.html#ReflectionFunctionAbstract::hasReturnType)
        — Checks if the function has a specified return type
    -   [ReflectionFunctionAbstract::inNamespace](/class/reflectionfunctionabstract.html#ReflectionFunctionAbstract::inNamespace)
        — Checks if function in namespace
    -   [ReflectionFunctionAbstract::isClosure](/class/reflectionfunctionabstract.html#ReflectionFunctionAbstract::isClosure)
        — Checks if closure
    -   [ReflectionFunctionAbstract::isDeprecated](/class/reflectionfunctionabstract.html#ReflectionFunctionAbstract::isDeprecated)
        — Checks if deprecated
    -   [ReflectionFunctionAbstract::isGenerator](/class/reflectionfunctionabstract.html#ReflectionFunctionAbstract::isGenerator)
        — Returns whether this function is a generator
    -   [ReflectionFunctionAbstract::isInternal](/class/reflectionfunctionabstract.html#ReflectionFunctionAbstract::isInternal)
        — Checks if is internal
    -   [ReflectionFunctionAbstract::isUserDefined](/class/reflectionfunctionabstract.html#ReflectionFunctionAbstract::isUserDefined)
        — Checks if user defined
    -   [ReflectionFunctionAbstract::isVariadic](/class/reflectionfunctionabstract.html#ReflectionFunctionAbstract::isVariadic)
        — Checks if the function is variadic
    -   [ReflectionFunctionAbstract::returnsReference](/class/reflectionfunctionabstract.html#ReflectionFunctionAbstract::returnsReference)
        — Checks if returns reference
    -   [ReflectionFunctionAbstract::\_\_toString](/class/reflectionfunctionabstract.html#ReflectionFunctionAbstract::__toString)
        — To string
-   [ReflectionMethod](/class/reflectionmethod.html) — The
    ReflectionMethod class
    -   [ReflectionMethod::\_\_construct](/class/reflectionmethod.html#ReflectionMethod::__construct)
        — Constructs a ReflectionMethod
    -   [ReflectionMethod::export](/class/reflectionmethod.html#ReflectionMethod::export)
        — Export a reflection method
    -   [ReflectionMethod::getClosure](/class/reflectionmethod.html#ReflectionMethod::getClosure)
        — Returns a dynamically created closure for the method
    -   [ReflectionMethod::getDeclaringClass](/class/reflectionmethod.html#ReflectionMethod::getDeclaringClass)
        — Gets declaring class for the reflected method
    -   [ReflectionMethod::getModifiers](/class/reflectionmethod.html#ReflectionMethod::getModifiers)
        — Gets the method modifiers
    -   [ReflectionMethod::getPrototype](/class/reflectionmethod.html#ReflectionMethod::getPrototype)
        — Gets the method prototype (if there is one)
    -   [ReflectionMethod::invoke](/class/reflectionmethod.html#ReflectionMethod::invoke)
        — Invoke
    -   [ReflectionMethod::invokeArgs](/class/reflectionmethod.html#ReflectionMethod::invokeArgs)
        — Invoke args
    -   [ReflectionMethod::isAbstract](/class/reflectionmethod.html#ReflectionMethod::isAbstract)
        — Checks if method is abstract
    -   [ReflectionMethod::isConstructor](/class/reflectionmethod.html#ReflectionMethod::isConstructor)
        — Checks if method is a constructor
    -   [ReflectionMethod::isDestructor](/class/reflectionmethod.html#ReflectionMethod::isDestructor)
        — Checks if method is a destructor
    -   [ReflectionMethod::isFinal](/class/reflectionmethod.html#ReflectionMethod::isFinal)
        — Checks if method is final
    -   [ReflectionMethod::isPrivate](/class/reflectionmethod.html#ReflectionMethod::isPrivate)
        — Checks if method is private
    -   [ReflectionMethod::isProtected](/class/reflectionmethod.html#ReflectionMethod::isProtected)
        — Checks if method is protected
    -   [ReflectionMethod::isPublic](/class/reflectionmethod.html#ReflectionMethod::isPublic)
        — Checks if method is public
    -   [ReflectionMethod::isStatic](/class/reflectionmethod.html#ReflectionMethod::isStatic)
        — Checks if method is static
    -   [ReflectionMethod::setAccessible](/class/reflectionmethod.html#ReflectionMethod::setAccessible)
        — Set method accessibility
    -   [ReflectionMethod::\_\_toString](/class/reflectionmethod.html#ReflectionMethod::__toString)
        — Returns the string representation of the Reflection method
        object
-   [ReflectionNamedType](/class/reflectionnamedtype.html) — The
    ReflectionNamedType class
    -   [ReflectionNamedType::getName](/class/reflectionnamedtype.html#ReflectionNamedType::getName)
        — Get the text of the type hint
-   [ReflectionObject](/class/reflectionobject.html) — The
    ReflectionObject class
    -   [ReflectionObject::\_\_construct](/class/reflectionobject.html#ReflectionObject::__construct)
        — Constructs a ReflectionObject
    -   [ReflectionObject::export](/class/reflectionobject.html#ReflectionObject::export)
        — Export
-   [ReflectionParameter](/class/reflectionparameter.html) — The
    ReflectionParameter class
    -   [ReflectionParameter::allowsNull](/class/reflectionparameter.html#ReflectionParameter::allowsNull)
        — Checks if null is allowed
    -   [ReflectionParameter::canBePassedByValue](/class/reflectionparameter.html#ReflectionParameter::canBePassedByValue)
        — Returns whether this parameter can be passed by value
    -   [ReflectionParameter::\_\_clone](/class/reflectionparameter.html#ReflectionParameter::__clone)
        — Clone
    -   [ReflectionParameter::\_\_construct](/class/reflectionparameter.html#ReflectionParameter::__construct)
        — Construct
    -   [ReflectionParameter::export](/class/reflectionparameter.html#ReflectionParameter::export)
        — Exports
    -   [ReflectionParameter::getClass](/class/reflectionparameter.html#ReflectionParameter::getClass)
        — Get the type hinted class
    -   [ReflectionParameter::getDeclaringClass](/class/reflectionparameter.html#ReflectionParameter::getDeclaringClass)
        — Gets declaring class
    -   [ReflectionParameter::getDeclaringFunction](/class/reflectionparameter.html#ReflectionParameter::getDeclaringFunction)
        — Gets declaring function
    -   [ReflectionParameter::getDefaultValue](/class/reflectionparameter.html#ReflectionParameter::getDefaultValue)
        — Gets default parameter value
    -   [ReflectionParameter::getDefaultValueConstantName](/class/reflectionparameter.html#ReflectionParameter::getDefaultValueConstantName)
        — Returns the default value's constant name if default value is
        constant or null
    -   [ReflectionParameter::getName](/class/reflectionparameter.html#ReflectionParameter::getName)
        — Gets parameter name
    -   [ReflectionParameter::getPosition](/class/reflectionparameter.html#ReflectionParameter::getPosition)
        — Gets parameter position
    -   [ReflectionParameter::getType](/class/reflectionparameter.html#ReflectionParameter::getType)
        — Gets a parameter's type
    -   [ReflectionParameter::hasType](/class/reflectionparameter.html#ReflectionParameter::hasType)
        — Checks if parameter has a type
    -   [ReflectionParameter::isArray](/class/reflectionparameter.html#ReflectionParameter::isArray)
        — Checks if parameter expects an array
    -   [ReflectionParameter::isCallable](/class/reflectionparameter.html#ReflectionParameter::isCallable)
        — Returns whether parameter MUST be callable
    -   [ReflectionParameter::isDefaultValueAvailable](/class/reflectionparameter.html#ReflectionParameter::isDefaultValueAvailable)
        — Checks if a default value is available
    -   [ReflectionParameter::isDefaultValueConstant](/class/reflectionparameter.html#ReflectionParameter::isDefaultValueConstant)
        — Returns whether the default value of this parameter is a
        constant
    -   [ReflectionParameter::isOptional](/class/reflectionparameter.html#ReflectionParameter::isOptional)
        — Checks if optional
    -   [ReflectionParameter::isPassedByReference](/class/reflectionparameter.html#ReflectionParameter::isPassedByReference)
        — Checks if passed by reference
    -   [ReflectionParameter::isVariadic](/class/reflectionparameter.html#ReflectionParameter::isVariadic)
        — Checks if the parameter is variadic
    -   [ReflectionParameter::\_\_toString](/class/reflectionparameter.html#ReflectionParameter::__toString)
        — To string
-   [ReflectionProperty](/class/reflectionproperty.html) — The
    ReflectionProperty class
    -   [ReflectionProperty::\_\_clone](/class/reflectionproperty.html#ReflectionProperty::__clone)
        — Clone
    -   [ReflectionProperty::\_\_construct](/class/reflectionproperty.html#ReflectionProperty::__construct)
        — Construct a ReflectionProperty object
    -   [ReflectionProperty::export](/class/reflectionproperty.html#ReflectionProperty::export)
        — Export
    -   [ReflectionProperty::getDeclaringClass](/class/reflectionproperty.html#ReflectionProperty::getDeclaringClass)
        — Gets declaring class
    -   [ReflectionProperty::getDefaultValue](/class/reflectionproperty.html#ReflectionProperty::getDefaultValue)
        — Returns the default value declared for a property
    -   [ReflectionProperty::getDocComment](/class/reflectionproperty.html#ReflectionProperty::getDocComment)
        — Gets the property doc comment
    -   [ReflectionProperty::getModifiers](/class/reflectionproperty.html#ReflectionProperty::getModifiers)
        — Gets the property modifiers
    -   [ReflectionProperty::getName](/class/reflectionproperty.html#ReflectionProperty::getName)
        — Gets property name
    -   [ReflectionProperty::getType](/class/reflectionproperty.html#ReflectionProperty::getType)
        — Gets a property's type
    -   [ReflectionProperty::getValue](/class/reflectionproperty.html#ReflectionProperty::getValue)
        — Gets value
    -   [ReflectionProperty::hasDefaultValue](/class/reflectionproperty.html#ReflectionProperty::hasDefaultValue)
        — Checks if property has a default value declared
    -   [ReflectionProperty::hasType](/class/reflectionproperty.html#ReflectionProperty::hasType)
        — Checks if property has a type
    -   [ReflectionProperty::isDefault](/class/reflectionproperty.html#ReflectionProperty::isDefault)
        — Checks if property is a default property
    -   [ReflectionProperty::isInitialized](/class/reflectionproperty.html#ReflectionProperty::isInitialized)
        — Checks whether a property is initialized
    -   [ReflectionProperty::isPrivate](/class/reflectionproperty.html#ReflectionProperty::isPrivate)
        — Checks if property is private
    -   [ReflectionProperty::isProtected](/class/reflectionproperty.html#ReflectionProperty::isProtected)
        — Checks if property is protected
    -   [ReflectionProperty::isPublic](/class/reflectionproperty.html#ReflectionProperty::isPublic)
        — Checks if property is public
    -   [ReflectionProperty::isStatic](/class/reflectionproperty.html#ReflectionProperty::isStatic)
        — Checks if property is static
    -   [ReflectionProperty::setAccessible](/class/reflectionproperty.html#ReflectionProperty::setAccessible)
        — Set property accessibility
    -   [ReflectionProperty::setValue](/class/reflectionproperty.html#ReflectionProperty::setValue)
        — Set property value
    -   [ReflectionProperty::\_\_toString](/class/reflectionproperty.html#ReflectionProperty::__toString)
        — To string
-   [ReflectionType](/class/reflectiontype.html) — The ReflectionType
    class
    -   [ReflectionType::allowsNull](/class/reflectiontype.html#ReflectionType::allowsNull)
        — Checks if null is allowed
    -   [ReflectionType::isBuiltin](/class/reflectiontype.html#ReflectionType::isBuiltin)
        — Checks if it is a built-in type
    -   [ReflectionType::\_\_toString](/class/reflectiontype.html#ReflectionType::__toString)
        — To string
-   [ReflectionGenerator](/class/reflectiongenerator.html) — The
    ReflectionGenerator class
    -   [ReflectionGenerator::\_\_construct](/class/reflectiongenerator.html#ReflectionGenerator::__construct)
        — Constructs a ReflectionGenerator object
    -   [ReflectionGenerator::getExecutingFile](/class/reflectiongenerator.html#ReflectionGenerator::getExecutingFile)
        — Gets the file name of the currently executing generator
    -   [ReflectionGenerator::getExecutingGenerator](/class/reflectiongenerator.html#ReflectionGenerator::getExecutingGenerator)
        — Gets the executing Generator object
    -   [ReflectionGenerator::getExecutingLine](/class/reflectiongenerator.html#ReflectionGenerator::getExecutingLine)
        — Gets the currently executing line of the generator
    -   [ReflectionGenerator::getFunction](/class/reflectiongenerator.html#ReflectionGenerator::getFunction)
        — Gets the function name of the generator
    -   [ReflectionGenerator::getThis](/class/reflectiongenerator.html#ReflectionGenerator::getThis)
        — Gets the $this value of the generator
    -   [ReflectionGenerator::getTrace](/class/reflectiongenerator.html#ReflectionGenerator::getTrace)
        — Gets the trace of the executing generator
-   [ReflectionReference](/class/reflectionreference.html) — The
    ReflectionReference class
    -   [ReflectionReference::fromArrayElement](/class/reflectionreference.html#ReflectionReference::fromArrayElement)
        — Create a ReflectionReference from an array element
    -   [ReflectionReference::getId](/class/reflectionreference.html#ReflectionReference::getId)
        — Get unique ID of a reference
-   [Reflector](/class/reflector.html) — The Reflector interface
    -   [Reflector::export](/class/reflector.html#Reflector::export) —
        Exports
    -   [Reflector::\_\_toString](/class/reflector.html#Reflector::__toString)
        — To string
-   [ReflectionException](/class/reflectionexception.html) — The
    ReflectionException class

Introduction
------------

The reflection class.

Class synopsis
--------------

**Reflection**

<span class="ooclass"> class **Reflection** </span> {

/\* Methods \*/

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">string</span> <span
class="methodname">export</span> ( <span class="methodparam"><span
class="type">Reflector</span> `$reflector`</span> \[, <span
class="methodparam"><span class="type">bool</span> `$return`<span
class="initializer"> = **`FALSE`**</span></span> \] )

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">array</span> <span
class="methodname">getModifierNames</span> ( <span
class="methodparam"><span class="type">int</span> `$modifiers`</span> )

}

Reflection::export
==================

Exports

**Warning**

This function has been *DEPRECATED* as of PHP 7.4.0. Relying on this
function is highly discouraged.

### Description

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">string</span> <span
class="methodname">Reflection::export</span> ( <span
class="methodparam"><span class="type">Reflector</span>
`$reflector`</span> \[, <span class="methodparam"><span
class="type">bool</span> `$return`<span class="initializer"> =
**`FALSE`**</span></span> \] )

Exports a reflection.

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`reflector`  
The reflection to export.

`return`  
Setting to **`TRUE`** will return the export, as opposed to emitting it.
Setting to **`FALSE`** (the default) will do the opposite.

### Return Values

If the `return` parameter is set to **`TRUE`**, then the export is
returned as a <span class="type">string</span>, otherwise **`NULL`** is
returned.

### See Also

-   <span class="methodname">Reflection::getModifierNames</span>

Reflection::getModifierNames
============================

Gets modifier names

### Description

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">array</span> <span
class="methodname">Reflection::getModifierNames</span> ( <span
class="methodparam"><span class="type">int</span> `$modifiers`</span> )

Gets modifier names.

### Parameters

`modifiers`  
Bitfield of the modifiers to get.

### Return Values

An array of modifier names.

### Examples

**Example \#1 <span
class="methodname">Reflection::getModifierNames</span> example**

``` php
<?php
class Testing
{
    final public static function foo()
    {
        return;
    }

    public function bar()
    {
        return;
    }
}

$foo = new ReflectionMethod('Testing', 'foo');

echo "Modifiers for method foo():\n";
echo $foo->getModifiers() . "\n";
echo implode(' ', Reflection::getModifierNames($foo->getModifiers())) . "\n";

$bar = new ReflectionMethod('Testing', 'bar');

echo "Modifiers for method bar():\n";
echo $bar->getModifiers() . "\n";
echo implode(' ', Reflection::getModifierNames($bar->getModifiers()));
```

The above example will output something similar to:

    Modifiers for method foo():
    261
    final public static
    Modifiers for method bar():
    65792
    public

### See Also

-   <span class="methodname">ReflectionClass::getModifiers</span>
-   <span
    class="methodname">ReflectionClassConstant::getModifiers</span>
-   <span class="methodname">ReflectionMethod::getModifiers</span>
-   <span class="methodname">ReflectionProperty::getModifiers</span>

Introduction
------------

The <span class="classname">ReflectionClass</span> class reports
information about a class.

Class synopsis
--------------

**ReflectionClass**

<span class="ooclass"> class **ReflectionClass** </span> <span
class="oointerface">implements <span
class="interfacename">Reflector</span> </span> {

/\* Constants \*/

<span class="modifier">const</span> <span class="type">int</span>
`ReflectionClass::IS_IMPLICIT_ABSTRACT` <span class="initializer"> =
16</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`ReflectionClass::IS_EXPLICIT_ABSTRACT` <span class="initializer"> =
32</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`ReflectionClass::IS_FINAL` <span class="initializer"> = 64</span> ;

/\* Properties \*/

<span class="modifier">public</span> `$name` ;

/\* Methods \*/

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> ( <span
class="methodparam"><span class="type">mixed</span> `$argument`</span> )

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">string</span> <span
class="methodname">export</span> ( <span class="methodparam"><span
class="type">mixed</span> `$argument`</span> \[, <span
class="methodparam"><span class="type">bool</span> `$return`<span
class="initializer"> = **`FALSE`**</span></span> \] )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">getConstant</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">getConstants</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="type">ReflectionMethod</span> <span
class="methodname">getConstructor</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">getDefaultProperties</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getDocComment</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getEndLine</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="type">ReflectionExtension</span> <span
class="methodname">getExtension</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getExtensionName</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getFileName</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">getInterfaceNames</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">getInterfaces</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="type">ReflectionMethod</span> <span
class="methodname">getMethod</span> ( <span class="methodparam"><span
class="type">string</span> `$name`</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">getMethods</span> (\[ <span
class="methodparam"><span class="type">int</span> `$filter`</span> \] )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getModifiers</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getName</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getNamespaceName</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="type">ReflectionClass</span> <span
class="methodname">getParentClass</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">getProperties</span> (\[ <span
class="methodparam"><span class="type">int</span> `$filter`</span> \] )

<span class="modifier">public</span> <span
class="type">ReflectionProperty</span> <span
class="methodname">getProperty</span> ( <span class="methodparam"><span
class="type">string</span> `$name`</span> )

<span class="modifier">public</span> <span
class="type">ReflectionClassConstant</span> <span
class="methodname">getReflectionConstant</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">getReflectionConstants</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getShortName</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getStartLine</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">getStaticProperties</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">getStaticPropertyValue</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> \[,
<span class="methodparam"><span class="type">mixed</span>
`&$def_value`</span> \] )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">getTraitAliases</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">getTraitNames</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">getTraits</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">hasConstant</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">hasMethod</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">hasProperty</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">implementsInterface</span> ( <span
class="methodparam"><span class="type">string</span> `$interface`</span>
)

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">inNamespace</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">isAbstract</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">isAnonymous</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">isCloneable</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">isFinal</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">isInstance</span> ( <span
class="methodparam"><span class="type">object</span> `$object`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">isInstantiable</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">isInterface</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">isInternal</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">isIterable</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">isSubclassOf</span> ( <span
class="methodparam"><span class="type">mixed</span> `$class`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">isTrait</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">isUserDefined</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">object</span>
<span class="methodname">newInstance</span> ( <span
class="methodparam"><span class="type">mixed</span> `$args`</span> )

<span class="modifier">public</span> <span class="type">object</span>
<span class="methodname">newInstanceArgs</span> (\[ <span
class="methodparam"><span class="type">array</span> `$args`</span> \] )

<span class="modifier">public</span> <span class="type">object</span>
<span class="methodname">newInstanceWithoutConstructor</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">setStaticPropertyValue</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> ,
<span class="methodparam"><span class="type">mixed</span>
`$value`</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">\_\_toString</span> ( <span
class="methodparam">void</span> )

}

Properties
----------

`name`  
Name of the class. Read-only, throws <span
class="classname">ReflectionException</span> in attempt to write.

Predefined Constants
--------------------

ReflectionClass Modifiers
-------------------------

**`ReflectionClass::IS_IMPLICIT_ABSTRACT`**  
Indicates class that is
<a href="/language/oop5/abstract.html" class="link">abstract</a> because
it has some abstract methods.

**`ReflectionClass::IS_EXPLICIT_ABSTRACT`**  
Indicates class that is
<a href="/language/oop5/abstract.html" class="link">abstract</a> because
of its definition.

**`ReflectionClass::IS_FINAL`**  
Indicates <a href="/language/oop5/final.html" class="link">final</a>
class.

ReflectionClass::\_\_construct
==============================

Constructs a ReflectionClass

### Description

<span class="modifier">public</span> <span
class="methodname">ReflectionClass::\_\_construct</span> ( <span
class="methodparam"><span class="type">mixed</span> `$argument`</span> )

Constructs a new <span class="classname">ReflectionClass</span> object.

### Parameters

`argument`  
Either a <span class="type">string</span> containing the name of the
class to reflect, or an <span class="type">object</span>.

### Return Values

Returns constructed <span class="classname">ReflectionClass</span>
instance.

### Errors/Exceptions

Throws <span class="classname">ReflectionException</span> if the class
to reflect does not exist.

### Examples

**Example \#1 Basic usage ReflectionClass**

``` php
<?php
Reflection::export(new ReflectionClass('Exception'));
?>
```

The above example will output something similar to:

    Class [ <internal:Core> class Exception ] {

      - Constants [0] {
      }

      - Static properties [0] {
      }

      - Static methods [0] {
      }

      - Properties [7] {
        Property [ <default> protected $message ]
        Property [ <default> private $string ]
        Property [ <default> protected $code ]
        Property [ <default> protected $file ]
        Property [ <default> protected $line ]
        Property [ <default> private $trace ]
        Property [ <default> private $previous ]
      }

      - Methods [10] {
        Method [ <internal:Core> final private method __clone ] {
        }

        Method [ <internal:Core, ctor> public method __construct ] {

          - Parameters [3] {
            Parameter #0 [ <optional> $message ]
            Parameter #1 [ <optional> $code ]
            Parameter #2 [ <optional> $previous ]
          }
        }

        Method [ <internal:Core> final public method getMessage ] {
        }

        Method [ <internal:Core> final public method getCode ] {
        }

        Method [ <internal:Core> final public method getFile ] {
        }

        Method [ <internal:Core> final public method getLine ] {
        }

        Method [ <internal:Core> final public method getTrace ] {
        }

        Method [ <internal:Core> final public method getPrevious ] {
        }

        Method [ <internal:Core> final public method getTraceAsString ] {
        }

        Method [ <internal:Core> public method __toString ] {
        }
      }
    }

### See Also

-   <span class="methodname">ReflectionObject::\_\_construct</span>
-   <a href="/language/oop5/decon.html#language.oop5.decon.constructor" class="link">Constructors</a>

ReflectionClass::export
=======================

Exports a class

**Warning**

This function has been *DEPRECATED* as of PHP 7.4.0. Relying on this
function is highly discouraged.

### Description

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">string</span> <span
class="methodname">ReflectionClass::export</span> ( <span
class="methodparam"><span class="type">mixed</span> `$argument`</span>
\[, <span class="methodparam"><span class="type">bool</span>
`$return`<span class="initializer"> = **`FALSE`**</span></span> \] )

Exports a reflected class.

### Parameters

`argument`  
The reflection to export.

`return`  
Setting to **`TRUE`** will return the export, as opposed to emitting it.
Setting to **`FALSE`** (the default) will do the opposite.

### Return Values

If the `return` parameter is set to **`TRUE`**, then the export is
returned as a <span class="type">string</span>, otherwise **`NULL`** is
returned.

### Examples

**Example \#1 Basic usage of <span
class="methodname">ReflectionClass::export</span>**

``` php
<?php
class Apple {
    public $var1;
    public $var2 = 'Orange';

    public function type() {
        return 'Apple';
    }
}
ReflectionClass::export('Apple');
?>
```

The above example will output something similar to:

    Class [ <user> class Apple ] {
      @@ php shell code 1-8

      - Constants [0] {
      }

      - Static properties [0] {
      }

      - Static methods [0] {
      }

      - Properties [2] {
        Property [ <default> public $var1 ]
        Property [ <default> public $var2 ]
      }

      - Methods [1] {
        Method [ <user> public method type ] {
          @@ php shell code 5 - 7
        }
      }
    }

### See Also

-   <span class="methodname">ReflectionClass::getName</span>
-   <span class="methodname">ReflectionClass::\_\_toString</span>

ReflectionClass::getConstant
============================

Gets defined constant

### Description

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">ReflectionClass::getConstant</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> )

Gets the defined constant.

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`name`  
The name of the class constant to get.

### Return Values

Value of the constant with the name `name`. Returns **`FALSE`** if the
constant was not found in the class.

### Examples

**Example \#1 Usage of <span
class="methodname">ReflectionClass::getConstant</span>**

``` php
<?php

class Example {
    const C1 = false;
    const C2 = 'I am a constant';
}

$reflection = new ReflectionClass('Example');

var_dump($reflection->getConstant('C1'));
var_dump($reflection->getConstant('C2'));
var_dump($reflection->getConstant('C3'));
?>
```

The above example will output:

    bool(false)
    string(15) "I am a constant"
    bool(false)

### See Also

-   <span class="methodname">ReflectionClass::getConstants</span>

ReflectionClass::getConstants
=============================

Gets constants

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">ReflectionClass::getConstants</span> ( <span
class="methodparam">void</span> )

Gets all defined constants from a class, regardless of their visibility.

### Parameters

This function has no parameters.

### Return Values

An <span class="type">array</span> of constants, where the keys hold the
name and the values the value of the constants.

### See Also

-   <span class="methodname">ReflectionClass::getConstant</span>

ReflectionClass::getConstructor
===============================

Gets the constructor of the class

### Description

<span class="modifier">public</span> <span
class="type">ReflectionMethod</span> <span
class="methodname">ReflectionClass::getConstructor</span> ( <span
class="methodparam">void</span> )

Gets the constructor of the reflected class.

### Parameters

This function has no parameters.

### Return Values

A <span class="classname">ReflectionMethod</span> object reflecting the
class' constructor, or **`NULL`** if the class has no constructor.

### Examples

**Example \#1 Basic usage of <span
class="methodname">ReflectionClass::getConstructor</span>**

``` php
<?php
$class = new ReflectionClass('ReflectionClass');
$constructor = $class->getConstructor();
var_dump($constructor);
?>
```

The above example will output:

    object(ReflectionMethod)#2 (2) {
      ["name"]=>
      string(11) "__construct"
      ["class"]=>
      string(15) "ReflectionClass"
    }

### See Also

-   <span class="methodname">ReflectionClass::getName</span>

ReflectionClass::getDefaultProperties
=====================================

Gets default properties

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">ReflectionClass::getDefaultProperties</span> (
<span class="methodparam">void</span> )

Gets default properties from a class (including inherited properties).

> **Note**:
>
> This method only works for static properties when used on internal
> classes. The default value of a static class property can not be
> tracked when using this method on user defined classes.

### Parameters

This function has no parameters.

### Return Values

An <span class="type">array</span> of default properties, with the key
being the name of the property and the value being the default value of
the property or **`NULL`** if the property doesn't have a default value.
The function does not distinguish between static and non static
properties and does not take visibility modifiers into account.

### Examples

**Example \#1 <span
class="methodname">ReflectionClass::getDefaultProperties</span>
example**

``` php
<?php
class Bar {
    protected $inheritedProperty = 'inheritedDefault';
}

class Foo extends Bar {
    public $property = 'propertyDefault';
    private $privateProperty = 'privatePropertyDefault';
    public static $staticProperty = 'staticProperty';
    public $defaultlessProperty;
}

$reflectionClass = new ReflectionClass('Foo');
var_dump($reflectionClass->getDefaultProperties());
?>
```

The above example will output:

    array(5) {
       ["staticProperty"]=>
       string(14) "staticProperty"
       ["property"]=>
       string(15) "propertyDefault"
       ["privateProperty"]=>
       string(22) "privatePropertyDefault"
       ["defaultlessProperty"]=>
       NULL
       ["inheritedProperty"]=>
       string(16) "inheritedDefault"
    }

### See Also

-   <span class="methodname">ReflectionClass::getProperties</span>
-   <span class="methodname">ReflectionClass::getStaticProperties</span>
-   <span class="methodname">ReflectionClass::getProperty</span>

ReflectionClass::getDocComment
==============================

Gets doc comments

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">ReflectionClass::getDocComment</span> ( <span
class="methodparam">void</span> )

Gets doc comments from a class. Doc comments start with /\*\*. If there
are multiple doc comments above the class definition, the one closest to
the class will be taken.

### Parameters

This function has no parameters.

### Return Values

The doc comment if it exists, otherwise **`FALSE`**

### Examples

**Example \#1 <span
class="methodname">ReflectionClass::getDocComment</span> example**

``` php
<?php
/** 
* A test class
*
* @param  foo bar
* @return baz
*/
class TestClass { }

$rc = new ReflectionClass('TestClass');
var_dump($rc->getDocComment())
?>
```

The above example will output:

    string(55) "/** 
    * A test class
    *
    * @param  foo bar
    * @return baz
    */"

### See Also

-   <span class="methodname">ReflectionClass::getName</span>

ReflectionClass::getEndLine
===========================

Gets end line

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">ReflectionClass::getEndLine</span> ( <span
class="methodparam">void</span> )

Gets end line number from a user-defined class definition.

### Parameters

This function has no parameters.

### Return Values

The ending line number of the user defined class, or **`FALSE`** if
unknown.

### Examples

**Example \#1 <span
class="methodname">ReflectionClass::getEndLine</span> example**

``` php
<?php
// Test Class
class TestClass { }

$rc = new ReflectionClass('TestClass');

echo $rc->getEndLine();
?>
```

The above example will output:

    3

### See Also

-   <span class="methodname">ReflectionClass::getStartLine</span>

ReflectionClass::getExtension
=============================

Gets a <span class="classname">ReflectionExtension</span> object for the
extension which defined the class

### Description

<span class="modifier">public</span> <span
class="type">ReflectionExtension</span> <span
class="methodname">ReflectionClass::getExtension</span> ( <span
class="methodparam">void</span> )

Gets a <span class="classname">ReflectionExtension</span> object for the
extension which defined the class.

### Parameters

This function has no parameters.

### Return Values

A <span class="classname">ReflectionExtension</span> object representing
the extension which defined the class, or **`NULL`** for user-defined
classes.

### Examples

**Example \#1 Basic usage of <span
class="methodname">ReflectionClass::getExtension</span>**

``` php
<?php
$class = new ReflectionClass('ReflectionClass');
$extension = $class->getExtension();
var_dump($extension);
?>
```

The above example will output:

    object(ReflectionExtension)#2 (1) {
      ["name"]=>
      string(10) "Reflection"
    }

### See Also

-   <span class="methodname">ReflectionClass::getExtensionName</span>

ReflectionClass::getExtensionName
=================================

Gets the name of the extension which defined the class

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">ReflectionClass::getExtensionName</span> (
<span class="methodparam">void</span> )

Gets the name of the extension which defined the class.

### Parameters

This function has no parameters.

### Return Values

The name of the extension which defined the class, or **`FALSE`** for
user-defined classes.

### Examples

**Example \#1 Basic usage of <span
class="methodname">ReflectionClass::getExtensionName</span>**

``` php
<?php
$class = new ReflectionClass('ReflectionClass');
$extension = $class->getExtensionName();
var_dump($extension);
?>
```

The above example will output:

    string(10) "Reflection"

### See Also

-   <span class="methodname">ReflectionClass::getExtension</span>

ReflectionClass::getFileName
============================

Gets the filename of the file in which the class has been defined

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">ReflectionClass::getFileName</span> ( <span
class="methodparam">void</span> )

Gets the filename of the file in which the class has been defined.

### Parameters

This function has no parameters.

### Return Values

Returns the filename of the file in which the class has been defined. If
the class is defined in the PHP core or in a PHP extension, **`FALSE`**
is returned.

### See Also

-   <span class="methodname">ReflectionClass::getExtensionName</span>

ReflectionClass::getInterfaceNames
==================================

Gets the interface names

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">ReflectionClass::getInterfaceNames</span> (
<span class="methodparam">void</span> )

Get the interface names.

### Parameters

This function has no parameters.

### Return Values

A numerical array with interface names as the values.

### Examples

**Example \#1 <span
class="methodname">ReflectionClass::getInterfaceNames</span> example**

``` php
<?php
interface Foo { }

interface Bar { }

class Baz implements Foo, Bar { }

$rc1 = new ReflectionClass("Baz");

print_r($rc1->getInterfaceNames());
?>
```

The above example will output something similar to:

    Array
    (
        [0] => Foo
        [1] => Bar
    )

### See Also

-   <span class="methodname">ReflectionClass::getInterfaces</span>

ReflectionClass::getInterfaces
==============================

Gets the interfaces

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">ReflectionClass::getInterfaces</span> ( <span
class="methodparam">void</span> )

Gets the interfaces.

### Parameters

This function has no parameters.

### Return Values

An associative <span class="type">array</span> of interfaces, with keys
as interface names and the array values as <span
class="classname">ReflectionClass</span> objects.

### Examples

**Example \#1 <span
class="methodname">ReflectionClass::getInterfaces</span> example**

``` php
<?php
interface Foo { }

interface Bar { }

class Baz implements Foo, Bar { }

$rc1 = new ReflectionClass("Baz");

print_r($rc1->getInterfaces());
?>
```

The above example will output something similar to:

    Array
    (
        [Foo] => ReflectionClass Object
            (
                [name] => Foo
            )

        [Bar] => ReflectionClass Object
            (
                [name] => Bar
            )

    )

### See Also

-   <span class="methodname">ReflectionClass::getInterfaceNames</span>

ReflectionClass::getMethod
==========================

Gets a <span class="classname">ReflectionMethod</span> for a class
method

### Description

<span class="modifier">public</span> <span
class="type">ReflectionMethod</span> <span
class="methodname">ReflectionClass::getMethod</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> )

Gets a <span class="classname">ReflectionMethod</span> for a class
method.

### Parameters

`name`  
The method name to reflect.

### Return Values

A <span class="classname">ReflectionMethod</span>.

### Errors/Exceptions

A <span class="classname">ReflectionException</span> if the method does
not exist.

### Examples

**Example \#1 Basic usage of <span
class="methodname">ReflectionClass::getMethod</span>**

``` php
<?php
$class = new ReflectionClass('ReflectionClass');
$method = $class->getMethod('getMethod');
var_dump($method);
?>
```

The above example will output:

    object(ReflectionMethod)#2 (2) {
      ["name"]=>
      string(9) "getMethod"
      ["class"]=>
      string(15) "ReflectionClass"
    }

### See Also

-   <span class="methodname">ReflectionClass::getMethods</span>

ReflectionClass::getMethods
===========================

Gets an array of methods

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">ReflectionClass::getMethods</span> (\[ <span
class="methodparam"><span class="type">int</span> `$filter`</span> \] )

Gets an array of methods for the class.

### Parameters

`filter`  
Filter the results to include only methods with certain attributes.
Defaults to no filtering.

Any bitwise disjunction of **`ReflectionMethod::IS_STATIC`**,
**`ReflectionMethod::IS_PUBLIC`**, **`ReflectionMethod::IS_PROTECTED`**,
**`ReflectionMethod::IS_PRIVATE`**, **`ReflectionMethod::IS_ABSTRACT`**,
**`ReflectionMethod::IS_FINAL`**, so that all methods with *any* of the
given attributes will be returned.

> **Note**: <span class="simpara"> Note that other bitwise operations,
> for instance *\~* will not work as expected. In other words, it is not
> possible to retrieve all non-static methods, for example. </span>

### Return Values

An <span class="type">array</span> of <span
class="classname">ReflectionMethod</span> objects reflecting each
method.

### Examples

**Example \#1 Basic usage of <span
class="methodname">ReflectionClass::getMethods</span>**

``` php
<?php
class Apple {
    public function firstMethod() { }
    final protected function secondMethod() { }
    private static function thirdMethod() { }
}

$class = new ReflectionClass('Apple');
$methods = $class->getMethods();
var_dump($methods);
?>
```

The above example will output:

    array(3) {
      [0]=>
      &object(ReflectionMethod)#2 (2) {
        ["name"]=>
        string(11) "firstMethod"
        ["class"]=>
        string(5) "Apple"
      }
      [1]=>
      &object(ReflectionMethod)#3 (2) {
        ["name"]=>
        string(12) "secondMethod"
        ["class"]=>
        string(5) "Apple"
      }
      [2]=>
      &object(ReflectionMethod)#4 (2) {
        ["name"]=>
        string(11) "thirdMethod"
        ["class"]=>
        string(5) "Apple"
      }
    }

**Example \#2 Filtering results from <span
class="methodname">ReflectionClass::getMethods</span>**

``` php
<?php
class Apple {
    public function firstMethod() { }
    final protected function secondMethod() { }
    private static function thirdMethod() { }
}

$class = new ReflectionClass('Apple');
$methods = $class->getMethods(ReflectionMethod::IS_STATIC | ReflectionMethod::IS_FINAL);
var_dump($methods);
?>
```

The above example will output:

    array(2) {
      [0]=>
      &object(ReflectionMethod)#2 (2) {
        ["name"]=>
        string(12) "secondMethod"
        ["class"]=>
        string(5) "Apple"
      }
      [1]=>
      &object(ReflectionMethod)#3 (2) {
        ["name"]=>
        string(11) "thirdMethod"
        ["class"]=>
        string(5) "Apple"
      }
    }

### See Also

-   <span class="methodname">ReflectionClass::getMethod</span>
-   <span class="function">get\_class\_methods</span>

ReflectionClass::getModifiers
=============================

Gets the class modifiers

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">ReflectionClass::getModifiers</span> ( <span
class="methodparam">void</span> )

Returns a bitfield of the access modifiers for this class.

### Parameters

This function has no parameters.

### Return Values

Returns bitmask of
<a href="/class/reflectionclass.html#ReflectionClass%20Modifiers" class="link">modifier constants</a>.

### See Also

-   <span class="methodname">ReflectionClass::getProperties</span>
-   <span class="methodname">Reflection::getModifierNames</span>

ReflectionClass::getName
========================

Gets class name

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">ReflectionClass::getName</span> ( <span
class="methodparam">void</span> )

Gets the class name.

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

The class name.

### Examples

**Example \#1 <span class="methodname">ReflectionClass::getName</span>
example**

``` php
<?php
namespace A\B;

class Foo { }

$function = new \ReflectionClass('stdClass');

var_dump($function->inNamespace());
var_dump($function->getName());
var_dump($function->getNamespaceName());
var_dump($function->getShortName());

$function = new \ReflectionClass('A\\B\\Foo');

var_dump($function->inNamespace());
var_dump($function->getName());
var_dump($function->getNamespaceName());
var_dump($function->getShortName());
?>
```

The above example will output:

    bool(false)
    string(8) "stdClass"
    string(0) ""
    string(8) "stdClass"

    bool(true)
    string(7) "A\B\Foo"
    string(3) "A\B"
    string(3) "Foo"

### See Also

-   <span class="methodname">ReflectionClass::getNamespaceName</span>

ReflectionClass::getNamespaceName
=================================

Gets namespace name

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">ReflectionClass::getNamespaceName</span> (
<span class="methodparam">void</span> )

Gets the namespace name.

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

The namespace name.

### Examples

**Example \#1 <span
class="methodname">ReflectionClass::getNamespaceName</span> example**

``` php
<?php
namespace A\B;

class Foo { }

$class = new \ReflectionClass('stdClass');

var_dump($class->inNamespace());
var_dump($class->getName());
var_dump($class->getNamespaceName());
var_dump($class->getShortName());

$class = new \ReflectionClass('A\\B\\Foo');

var_dump($class->inNamespace());
var_dump($class->getName());
var_dump($class->getNamespaceName());
var_dump($class->getShortName());
?>
```

The above example will output:

    bool(false)
    string(8) "stdClass"
    string(0) ""
    string(8) "stdClass"

    bool(true)
    string(7) "A\B\Foo"
    string(3) "A\B"
    string(3) "Foo"

### See Also

-   <span class="methodname">ReflectionClass::getParentClass</span>
-   <a href="/language/namespaces.html" class="link">namespaces</a>

ReflectionClass::getParentClass
===============================

Gets parent class

### Description

<span class="modifier">public</span> <span
class="type">ReflectionClass</span> <span
class="methodname">ReflectionClass::getParentClass</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

A <span class="classname">ReflectionClass</span> or **`FALSE`** if
there's no parent.

### See Also

-   <span class="methodname">ReflectionClass::\_\_construct</span>

ReflectionClass::getProperties
==============================

Gets properties

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">ReflectionClass::getProperties</span> (\[ <span
class="methodparam"><span class="type">int</span> `$filter`</span> \] )

Retrieves reflected properties.

### Parameters

`filter`  
The optional filter, for filtering desired property types. It's
configured using the
<a href="/class/reflectionproperty.html#ReflectionProperty%20Modifiers" class="link">ReflectionProperty constants</a>,
and defaults to all property types.

### Return Values

An array of <span class="classname">ReflectionProperty</span> objects.

### Examples

**Example \#1 <span
class="function">ReflectionClass::getProperties</span> filtering
example**

This example demonstrates usage of the optional `filter` parameter,
where it essentially skips private properties.

``` php
<?php
class Foo {
    public    $foo  = 1;
    protected $bar  = 2;
    private   $baz  = 3;
}

$foo = new Foo();

$reflect = new ReflectionClass($foo);
$props   = $reflect->getProperties(ReflectionProperty::IS_PUBLIC | ReflectionProperty::IS_PROTECTED);

foreach ($props as $prop) {
    print $prop->getName() . "\n";
}

var_dump($props);

?>
```

The above example will output something similar to:

    foo
    bar
    array(2) {
      [0]=>
      object(ReflectionProperty)#3 (2) {
        ["name"]=>
        string(3) "foo"
        ["class"]=>
        string(3) "Foo"
      }
      [1]=>
      object(ReflectionProperty)#4 (2) {
        ["name"]=>
        string(3) "bar"
        ["class"]=>
        string(3) "Foo"
      }
    }

### See Also

-   <span class="methodname">ReflectionClass::getProperty</span>
-   <span class="classname">ReflectionProperty</span>
-   <a href="/class/reflectionproperty.html#ReflectionProperty%20Modifiers" class="link">ReflectionProperty modifier constants</a>

ReflectionClass::getProperty
============================

Gets a <span class="classname">ReflectionProperty</span> for a class's
property

### Description

<span class="modifier">public</span> <span
class="type">ReflectionProperty</span> <span
class="methodname">ReflectionClass::getProperty</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> )

Gets a <span class="classname">ReflectionProperty</span> for a class's
property.

### Parameters

`name`  
The property name.

### Return Values

A <span class="classname">ReflectionProperty</span>.

### Examples

**Example \#1 Basic usage of <span
class="methodname">ReflectionClass::getProperty</span>**

``` php
<?php
$class = new ReflectionClass('ReflectionClass');
$property = $class->getProperty('name');
var_dump($property);
?>
```

The above example will output:

    object(ReflectionProperty)#2 (2) {
      ["name"]=>
      string(4) "name"
      ["class"]=>
      string(15) "ReflectionClass"
    }

### See Also

-   <span class="methodname">ReflectionClass::getProperties</span>

ReflectionClass::getReflectionConstant
======================================

Gets a <span class="classname">ReflectionClassConstant</span> for a
class's constant

### Description

<span class="modifier">public</span> <span
class="type">ReflectionClassConstant</span> <span
class="methodname">ReflectionClass::getReflectionConstant</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> )

Gets a <span class="classname">ReflectionClassConstant</span> for a
class's property.

### Parameters

`name`  
The class constant name.

### Return Values

A <span class="classname">ReflectionClassConstant</span>.

### See Also

-   <span
    class="methodname">ReflectionClass::getReflectionConstants</span>
-   <span class="classname">ReflectionClassConstant</span>

ReflectionClass::getReflectionConstants
=======================================

Gets class constants

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">ReflectionClass::getReflectionConstants</span>
( <span class="methodparam">void</span> )

Retrieves reflected constants.

### Parameters

This function has no parameters.

### Return Values

An array of <span class="classname">ReflectionClassConstant</span>
objects.

### Examples

**Example \#1 Basic <span
class="function">ReflectionClass::getReflectionConstants</span>
example**

``` php
<?php
class Foo {
    public    const FOO  = 1;
    protected const BAR  = 2;
    private   const BAZ  = 3;
}

$foo = new Foo();

$reflect = new ReflectionClass($foo);
$consts  = $reflect->getReflectionConstants();

foreach ($consts as $const) {
    print $const->getName() . "\n";
}

var_dump($consts);

?>
```

The above example will output something similar to:

    FOO
    BAR
    BAZ
    array(3) {
      [0]=>
      object(ReflectionClassConstant)#3 (2) {
        ["name"]=>
        string(3) "FOO"
        ["class"]=>
        string(3) "Foo"
      }
      [1]=>
      object(ReflectionClassConstant)#4 (2) {
        ["name"]=>
        string(3) "BAR"
        ["class"]=>
        string(3) "Foo"
      }
      [2]=>
      object(ReflectionClassConstant)#5 (2) {
        ["name"]=>
        string(3) "BAZ"
        ["class"]=>
        string(3) "Foo"
      }
    }

### See Also

-   <span
    class="methodname">ReflectionClass::getReflectionConstant</span>
-   <span class="classname">ReflectionClassConstant</span>

ReflectionClass::getShortName
=============================

Gets short name

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">ReflectionClass::getShortName</span> ( <span
class="methodparam">void</span> )

Gets the short name of the class, the part without the namespace.

### Parameters

This function has no parameters.

### Return Values

The class short name.

### Examples

**Example \#1 <span
class="methodname">ReflectionClass::getShortName</span> example**

``` php
<?php
namespace A\B;

class Foo { }

$function = new \ReflectionClass('stdClass');

var_dump($function->inNamespace());
var_dump($function->getName());
var_dump($function->getNamespaceName());
var_dump($function->getShortName());

$function = new \ReflectionClass('A\\B\\Foo');

var_dump($function->inNamespace());
var_dump($function->getName());
var_dump($function->getNamespaceName());
var_dump($function->getShortName());
?>
```

The above example will output:

    bool(false)
    string(8) "stdClass"
    string(0) ""
    string(8) "stdClass"

    bool(true)
    string(7) "A\B\Foo"
    string(3) "A\B"
    string(3) "Foo"

### See Also

-   <span class="methodname">ReflectionClass::getName</span>

ReflectionClass::getStartLine
=============================

Gets starting line number

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">ReflectionClass::getStartLine</span> ( <span
class="methodparam">void</span> )

Get the starting line number.

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

The starting line number, as an <span class="type">int</span>.

### See Also

-   <span class="methodname">ReflectionClass::getEndLine</span>

ReflectionClass::getStaticProperties
====================================

Gets static properties

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">ReflectionClass::getStaticProperties</span> (
<span class="methodparam">void</span> )

Get the static properties.

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

The static properties, as an <span class="type">array</span>.

### See Also

-   <span
    class="methodname">ReflectionClass::getStaticPropertyValue</span>
-   <span
    class="methodname">ReflectionClass::setStaticPropertyValue</span>

ReflectionClass::getStaticPropertyValue
=======================================

Gets static property value

### Description

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">ReflectionClass::getStaticPropertyValue</span>
( <span class="methodparam"><span class="type">string</span>
`$name`</span> \[, <span class="methodparam"><span
class="type">mixed</span> `&$def_value`</span> \] )

Gets the value of a static property on this class.

### Parameters

`name`  
The name of the static property for which to return a value.

`def_value`  
A default value to return in case the class does not declare a static
property with the given `name`. If the property does not exist and this
argument is omitted, a <span
class="classname">ReflectionException</span> is thrown.

### Return Values

The value of the static property.

### Examples

**Example \#1 Basic usage of <span
class="methodname">ReflectionClass::getStaticPropertyValue</span>**

``` php
<?php
class Apple {
    public static $color = 'Red';
}

$class = new ReflectionClass('Apple');
var_dump($class->getStaticPropertyValue('color'));
?>
```

The above example will output:

    string(3) "Red"

### See Also

-   <span class="methodname">ReflectionClass::getStaticProperties</span>
-   <span
    class="methodname">ReflectionClass::setStaticPropertyValue</span>

ReflectionClass::getTraitAliases
================================

Returns an array of trait aliases

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">ReflectionClass::getTraitAliases</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

Returns an array with new method names in keys and original names (in
the format *"TraitName::original"*) in values. Returns **`NULL`** in
case of an error.

ReflectionClass::getTraitNames
==============================

Returns an array of names of traits used by this class

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">ReflectionClass::getTraitNames</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

Returns an array with trait names in values. Returns **`NULL`** in case
of an error.

ReflectionClass::getTraits
==========================

Returns an array of traits used by this class

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">ReflectionClass::getTraits</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

Returns an array with trait names in keys and instances of trait's <span
class="classname">ReflectionClass</span> in values. Returns **`NULL`**
in case of an error.

ReflectionClass::hasConstant
============================

Checks if constant is defined

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ReflectionClass::hasConstant</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> )

Checks whether the class has a specific constant defined or not.

### Parameters

`name`  
The name of the constant being checked for.

### Return Values

**`TRUE`** if the constant is defined, otherwise **`FALSE`**.

### Examples

**Example \#1 <span
class="methodname">ReflectionClass::hasConstant</span> example**

``` php
<?php
class Foo {
    const c1 = 1;
}

$class = new ReflectionClass("Foo");

var_dump($class->hasConstant("c1"));
var_dump($class->hasConstant("c2"));
?>
```

The above example will output something similar to:

    bool(true)
    bool(false)

### See Also

-   <span class="methodname">ReflectionClass::hasMethod</span>
-   <span class="methodname">ReflectionClass::hasProperty</span>

ReflectionClass::hasMethod
==========================

Checks if method is defined

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ReflectionClass::hasMethod</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> )

Checks whether a specific method is defined in a class.

### Parameters

`name`  
Name of the method being checked for.

### Return Values

**`TRUE`** if it has the method, otherwise **`FALSE`**

### Examples

**Example \#1 <span class="methodname">ReflectionClass::hasMethod</span>
example**

``` php
<?php
Class C {
    public function publicFoo() {
        return true;
    }

    protected function protectedFoo() {
        return true;
    }

    private function privateFoo() {
        return true;
    }

    static function staticFoo() {
        return true;
    }
}

$rc = new ReflectionClass("C");

var_dump($rc->hasMethod('publicFoo'));

var_dump($rc->hasMethod('protectedFoo'));

var_dump($rc->hasMethod('privateFoo'));

var_dump($rc->hasMethod('staticFoo'));

// C should not have method bar
var_dump($rc->hasMethod('bar'));

// Method names are case insensitive
var_dump($rc->hasMethod('PUBLICfOO'));
?>
```

The above example will output:

    bool(true)
    bool(true)
    bool(true)
    bool(true)
    bool(false)
    bool(true)

### See Also

-   <span class="methodname">ReflectionClass::hasConstant</span>
-   <span class="methodname">ReflectionClass::hasProperty</span>

ReflectionClass::hasProperty
============================

Checks if property is defined

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ReflectionClass::hasProperty</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> )

Checks whether the specified property is defined.

### Parameters

`name`  
Name of the property being checked for.

### Return Values

**`TRUE`** if it has the property, otherwise **`FALSE`**

### Examples

**Example \#1 <span
class="methodname">ReflectionClass::hasProperty</span> example**

``` php
<?php
class Foo {
    public    $p1;
    protected $p2;
    private   $p3;

}

$obj = new ReflectionObject(new Foo());

var_dump($obj->hasProperty("p1"));
var_dump($obj->hasProperty("p2"));
var_dump($obj->hasProperty("p3"));
var_dump($obj->hasProperty("p4"));
?>
```

The above example will output something similar to:

    bool(true)
    bool(true)
    bool(true)
    bool(false)

### See Also

-   <span class="methodname">ReflectionClass::hasConstant</span>
-   <span class="methodname">ReflectionClass::hasMethod</span>

ReflectionClass::implementsInterface
====================================

Implements interface

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ReflectionClass::implementsInterface</span> (
<span class="methodparam"><span class="type">string</span>
`$interface`</span> )

Checks whether it implements an interface.

### Parameters

`interface`  
The interface name.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### See Also

-   <span class="methodname">ReflectionClass::isInterface</span>
-   <span class="methodname">ReflectionClass::isSubclassOf</span>
-   <span class="function">interface\_exists</span>
-   <a href="/language/oop5/interfaces.html" class="link">Object Interfaces</a>

ReflectionClass::inNamespace
============================

Checks if in namespace

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ReflectionClass::inNamespace</span> ( <span
class="methodparam">void</span> )

Checks if this class is defined in a namespace.

### Parameters

This function has no parameters.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 <span
class="methodname">ReflectionClass::inNamespace</span> example**

``` php
<?php
namespace A\B;

class Foo { }

$function = new \ReflectionClass('stdClass');

var_dump($function->inNamespace());
var_dump($function->getName());
var_dump($function->getNamespaceName());
var_dump($function->getShortName());

$function = new \ReflectionClass('A\\B\\Foo');

var_dump($function->inNamespace());
var_dump($function->getName());
var_dump($function->getNamespaceName());
var_dump($function->getShortName());
?>
```

The above example will output:

    bool(false)
    string(8) "stdClass"
    string(0) ""
    string(8) "stdClass"

    bool(true)
    string(7) "A\B\Foo"
    string(3) "A\B"
    string(3) "Foo"

### See Also

-   <span class="methodname">ReflectionClass::getNamespaceName</span>
-   <a href="/language/namespaces.html" class="link">PHP Namespaces</a>

ReflectionClass::isAbstract
===========================

Checks if class is abstract

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ReflectionClass::isAbstract</span> ( <span
class="methodparam">void</span> )

Checks if the class is abstract.

### Parameters

This function has no parameters.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 <span
class="methodname">ReflectionClass::isAbstract</span> example**

``` php
<?php
class          TestClass { }
abstract class TestAbstractClass { }

$testClass     = new ReflectionClass('TestClass');
$abstractClass = new ReflectionClass('TestAbstractClass');

var_dump($testClass->isAbstract());
var_dump($abstractClass->isAbstract());
?>
```

The above example will output:

    bool(false)
    bool(true)

### See Also

-   <span class="methodname">ReflectionClass::isInterface</span>
-   <a href="/language/oop5/abstract.html" class="link">Class Abstraction</a>

ReflectionClass::isAnonymous
============================

Checks if class is anonymous

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ReflectionClass::isAnonymous</span> ( <span
class="methodparam">void</span> )

Checks if a class is an anonymous class.

### Parameters

This function has no parameters.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 <span
class="methodname">ReflectionClass::isAnonymous</span> example**

``` php
<?php
class TestClass {}
$anonClass = new class {};

$normalClass = new ReflectionClass('TestClass');
$anonClass  = new ReflectionClass($anonClass);

var_dump($normalClass->isAnonymous());
var_dump($anonClass->isAnonymous());

?>
```

The above example will output:

    bool(false)
    bool(true)

### See Also

-   <span class="methodname">ReflectionClass::isFinal</span>

ReflectionClass::isCloneable
============================

Returns whether this class is cloneable

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ReflectionClass::isCloneable</span> ( <span
class="methodparam">void</span> )

Returns whether this class is cloneable.

### Parameters

This function has no parameters.

### Return Values

Returns **`TRUE`** if the class is cloneable, **`FALSE`** otherwise.

### Examples

**Example \#1 Basic usage of <span
class="methodname">ReflectionClass::isCloneable</span>**

``` php
<?php
class NotCloneable {
    public $var1;
    
    private function __clone() {
    }
}

class Cloneable {
    public $var1;
}

$notCloneable = new ReflectionClass('NotCloneable');
$cloneable = new ReflectionClass('Cloneable');

var_dump($notCloneable->isCloneable());
var_dump($cloneable->isCloneable());
?>
```

The above example will output:

    bool(false)
    bool(true)

ReflectionClass::isFinal
========================

Checks if class is final

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ReflectionClass::isFinal</span> ( <span
class="methodparam">void</span> )

Checks if a class is final.

### Parameters

This function has no parameters.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 <span class="methodname">ReflectionClass::isFinal</span>
example**

``` php
<?php
class       TestClass { }
final class TestFinalClass { }

$normalClass = new ReflectionClass('TestClass');
$finalClass  = new ReflectionClass('TestFinalClass');

var_dump($normalClass->isFinal());
var_dump($finalClass->isFinal());

?>
```

The above example will output:

    bool(false)
    bool(true)

### See Also

-   <span class="methodname">ReflectionClass::isAbstract</span>
-   <a href="/language/oop5/final.html" class="link">Final Keyword</a>

ReflectionClass::isInstance
===========================

Checks class for instance

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ReflectionClass::isInstance</span> ( <span
class="methodparam"><span class="type">object</span> `$object`</span> )

Checks if an object is an instance of a class.

### Parameters

`object`  
The object being compared to.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 <span
class="methodname">ReflectionClass::isInstance</span> related examples**

``` php
<?php
// Example usage
$class = new ReflectionClass('Foo');

if ($class->isInstance($arg)) {
    echo "Yes";
}

// Equivalent to
if ($arg instanceof Foo) {
    echo "Yes";
}

// Equivalent to
if (is_a($arg, 'Foo')) {
    echo "Yes";
}
?>
```

The above example will output something similar to:

    Yes
    Yes
    Yes

### See Also

-   <span class="methodname">ReflectionClass::isInterface</span>
-   <a href="/language/operators/type.html" class="link">Type operators (instanceof)</a>
-   <a href="/language/oop5/interfaces.html" class="link">Object Interfaces</a>
-   <span class="function">is\_a</span>

ReflectionClass::isInstantiable
===============================

Checks if the class is instantiable

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ReflectionClass::isInstantiable</span> ( <span
class="methodparam">void</span> )

Checks if the class is instantiable.

### Parameters

This function has no parameters.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 <span
class="methodname">ReflectionClass::isInstantiable</span> example**

``` php
<?php
class C { }

interface iface {
    function f1();
}

class ifaceImpl implements iface {
    function f1() {}
}

abstract class abstractClass {
    function f1() { }
    abstract function f2();
}

class D extends abstractClass {
    function f2() { }
}

trait T {
    function f1() {}
}

class privateConstructor {
    private function __construct() { }
}

$classes = array(
    "C",
    "iface",
    "ifaceImpl",
    "abstractClass",
    "D",
    "T",
    "privateConstructor",
);

foreach($classes  as $class ) {
    $reflectionClass = new ReflectionClass($class);
    echo "Is $class instantiable?  ";
    var_dump($reflectionClass->isInstantiable()); 
}

?>
```

The above example will output:

    Is C instantiable?  bool(true)
    Is iface instantiable?  bool(false)
    Is ifaceImpl instantiable?  bool(true)
    Is abstractClass instantiable?  bool(false)
    Is D instantiable?  bool(true)
    Is T instantiable?  bool(false)
    Is privateConstructor instantiable?  bool(false)

### See Also

-   <span class="methodname">ReflectionClass::isInstance</span>

ReflectionClass::isInterface
============================

Checks if the class is an interface

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ReflectionClass::isInterface</span> ( <span
class="methodparam">void</span> )

Checks whether the class is an interface.

### Parameters

This function has no parameters.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 Basic usage of <span
class="methodname">ReflectionClass::isInterface</span>**

``` php
<?php
interface SomeInterface {
    public function interfaceMethod();
}

$class = new ReflectionClass('SomeInterface');
var_dump($class->isInterface());
?>
```

The above example will output:

    bool(true)

### See Also

-   <span class="methodname">ReflectionClass::isInstance</span>

ReflectionClass::isInternal
===========================

Checks if class is defined internally by an extension, or the core

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ReflectionClass::isInternal</span> ( <span
class="methodparam">void</span> )

Checks if the class is defined internally by an extension, or the core,
as opposed to user-defined.

### Parameters

This function has no parameters.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 Basic usage of <span
class="methodname">ReflectionClass::isInternal</span>**

``` php
<?php
$internalclass = new ReflectionClass('ReflectionClass');

class Apple {}
$userclass = new ReflectionClass('Apple');

var_dump($internalclass->isInternal());
var_dump($userclass->isInternal());
?>
```

The above example will output:

    bool(true)
    bool(false)

### See Also

-   <span class="methodname">ReflectionClass::isUserDefined</span>

ReflectionClass::isIterable
===========================

Check whether this class is iterable

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ReflectionClass::isIterable</span> ( <span
class="methodparam">void</span> )

Check whether this class is iterable (i.e. can be used inside
<a href="/control-structures/foreach.html" class="link">foreach</a>).

### Parameters

This function has no parameters.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 Basic <span
class="methodname">ReflectionClass::isIterable</span> Usage**

``` php
<?php

class IteratorClass implements Iterator {
    public function __construct() { }
    public function key() { }
    public function current() { }
    function next() { }
    function valid() { }
    function rewind() { }
}
class DerivedClass extends IteratorClass { }
class NonIterator { }

function dump_iterable($class) {
    $reflection = new ReflectionClass($class);
    var_dump($reflection->isIterable());
}

$classes = array("ArrayObject", "IteratorClass", "DerivedClass", "NonIterator");

foreach ($classes as $class) {
    echo "Is $class iterable? ";
    dump_iterable($class);
}
?>
```

The above example will output:

    Is ArrayObject iterable? bool(true)
    Is IteratorClass iterable? bool(true)
    Is DerivedClass iterable? bool(true)
    Is NonIterator iterable? bool(false)

### See Also

-   <span class="methodname">ReflectionClass::\_\_construct</span>

ReflectionClass::isIterateable
==============================

Alias of <span class="methodname">ReflectionClass::isIterable</span>

### Description

Alias of <span class="methodname">ReflectionClass::isIterable</span>

As of PHP 7.2.0, instead of the missspelled <span
class="methodname">RefectionClass::isIterateable</span>, <span
class="methodname">ReflectionClass::isIterable</span> should be
preferred.

ReflectionClass::isSubclassOf
=============================

Checks if a subclass

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ReflectionClass::isSubclassOf</span> ( <span
class="methodparam"><span class="type">mixed</span> `$class`</span> )

Checks if the class is a subclass of a specified class or implements a
specified interface.

### Parameters

`class`  
Either the name of the class as <span class="type">string</span> or a
<span class="type">ReflectionClass</span> object of the class to check
against.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### See Also

-   <span class="methodname">ReflectionClass::isInterface</span>
-   <span class="methodname">ReflectionClass::implementsInterface</span>
-   <span class="function">is\_subclass\_of</span>
-   <span class="function">get\_parent\_class</span>

ReflectionClass::isTrait
========================

Returns whether this is a trait

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ReflectionClass::isTrait</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

Returns **`TRUE`** if this is a trait, **`FALSE`** otherwise. Returns
**`NULL`** in case of an error.

ReflectionClass::isUserDefined
==============================

Checks if user defined

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ReflectionClass::isUserDefined</span> ( <span
class="methodparam">void</span> )

Checks whether the class is user-defined, as opposed to internal.

### Parameters

This function has no parameters.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### See Also

-   <span class="methodname">ReflectionClass::isInternal</span>

ReflectionClass::newInstance
============================

Creates a new class instance from given arguments

### Description

<span class="modifier">public</span> <span class="type">object</span>
<span class="methodname">ReflectionClass::newInstance</span> ( <span
class="methodparam"><span class="type">mixed</span> `$args`</span> )

Creates a new instance of the class. The given arguments are passed to
the class constructor.

### Parameters

`args`  
Accepts a variable number of arguments which are passed to the class
constructor, much like <span class="function">call\_user\_func</span>.

### Return Values

### Errors/Exceptions

A <span class="classname">ReflectionException</span> if the class
constructor is not public.

A <span class="classname">ReflectionException</span> if the class does
not have a constructor and the `args` parameter contains one or more
parameters.

### See Also

-   <span class="methodname">ReflectionClass::newInstanceArgs</span>
-   <span
    class="methodname">ReflectionClass::newInstanceWithoutConstructor</span>

ReflectionClass::newInstanceArgs
================================

Creates a new class instance from given arguments

### Description

<span class="modifier">public</span> <span class="type">object</span>
<span class="methodname">ReflectionClass::newInstanceArgs</span> (\[
<span class="methodparam"><span class="type">array</span> `$args`</span>
\] )

Creates a new instance of the class, the given arguments are passed to
the class constructor.

### Parameters

`args`  
The parameters to be passed to the class constructor as an <span
class="type">array</span>.

### Return Values

Returns a new instance of the class.

### Examples

**Example \#1 Basic usage of <span
class="methodname">ReflectionClass::newInstanceArgs</span>**

``` php
<?php
$class = new ReflectionClass('ReflectionFunction');
$instance = $class->newInstanceArgs(array('substr'));
var_dump($instance);
?>
```

The above example will output:

    object(ReflectionFunction)#2 (1) {
      ["name"]=>
      string(6) "substr"
    }

### Errors/Exceptions

A <span class="classname">ReflectionException</span> if the class
constructor is not public.

A <span class="classname">ReflectionException</span> if the class does
not have a constructor and the `args` parameter contains one or more
parameters.

### See Also

-   <span class="methodname">ReflectionClass::newInstance</span>
-   <span
    class="methodname">ReflectionClass::newInstanceWithoutConstructor</span>

ReflectionClass::newInstanceWithoutConstructor
==============================================

Creates a new class instance without invoking the constructor

### Description

<span class="modifier">public</span> <span class="type">object</span>
<span
class="methodname">ReflectionClass::newInstanceWithoutConstructor</span>
( <span class="methodparam">void</span> )

Creates a new instance of the class without invoking the constructor.

### Parameters

### Return Values

### Changelog

| Version | Description                                                                                                                        |
|---------|------------------------------------------------------------------------------------------------------------------------------------|
| 5.6.0   | All internal classes can now be instantiated except for those declared <a href="/language/oop5/final.html" class="link">final</a>. |

### Errors/Exceptions

A <span class="classname">ReflectionException</span> if the class is an
internal class that cannot be instantiated without invoking the
constructor. In PHP 5.6.0 onwards, this exception is limited only to
internal classes that are
<a href="/language/oop5/final.html" class="link">final</a>.

### See Also

-   <span class="methodname">ReflectionClass::newInstance</span>
-   <span class="methodname">ReflectionClass::newInstanceArgs</span>

ReflectionClass::setStaticPropertyValue
=======================================

Sets static property value

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">ReflectionClass::setStaticPropertyValue</span>
( <span class="methodparam"><span class="type">string</span>
`$name`</span> , <span class="methodparam"><span
class="type">mixed</span> `$value`</span> )

Sets static property value.

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`name`  
Property name.

`value`  
New property value.

### Return Values

No value is returned.

### See Also

-   <span
    class="methodname">ReflectionClass::getStaticPropertyValue</span>

ReflectionClass::\_\_toString
=============================

Returns the string representation of the ReflectionClass object

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">ReflectionClass::\_\_toString</span> ( <span
class="methodparam">void</span> )

Returns the string representation of the ReflectionClass object.

### Parameters

This function has no parameters.

### Return Values

A string representation of this <span
class="classname">ReflectionClass</span> instance.

### Examples

**Example \#1 <span
class="methodname">ReflectionClass::\_\_toString</span> example**

``` php
<?php
$reflectionClass = new ReflectionClass('Exception');
echo $reflectionClass->__toString();
?>
```

The above example will output:

    Class [ <internal:Core> class Exception ] {

      - Constants [0] {
      }

      - Static properties [0] {
      }

      - Static methods [0] {
      }

      - Properties [7] {
        Property [ <default> protected $message ]
        Property [ <default> private $string ]
        Property [ <default> protected $code ]
        Property [ <default> protected $file ]
        Property [ <default> protected $line ]
        Property [ <default> private $trace ]
        Property [ <default> private $previous ]
      }

      - Methods [10] {
        Method [ <internal:Core> final private method __clone ] {
        }

        Method [ <internal:Core, ctor> public method __construct ] {

          - Parameters [3] {
            Parameter #0 [ <optional> $message ]
            Parameter #1 [ <optional> $code ]
            Parameter #2 [ <optional> $previous ]
          }
        }

        Method [ <internal:Core> final public method getMessage ] {
        }

        Method [ <internal:Core> final public method getCode ] {
        }

        Method [ <internal:Core> final public method getFile ] {
        }

        Method [ <internal:Core> final public method getLine ] {
        }

        Method [ <internal:Core> final public method getTrace ] {
        }

        Method [ <internal:Core> final public method getPrevious ] {
        }

        Method [ <internal:Core> final public method getTraceAsString ] {
        }

        Method [ <internal:Core> public method __toString ] {
        }
      }
    }

### See Also

-   <span class="methodname">ReflectionClass::export</span>
-   <a href="/language/oop5/magic.html#object.tostring" class="link">__toString()</a>

Introduction
------------

The <span class="classname">ReflectionClassConstant</span> class reports
information about a class constant.

Class synopsis
--------------

**ReflectionClassConstant**

<span class="ooclass"> class **ReflectionClassConstant** </span> <span
class="oointerface">implements <span
class="interfacename">Reflector</span> </span> {

/\* Properties \*/

<span class="modifier">public</span> `$name` ;

<span class="modifier">public</span> `$class` ;

/\* Methods \*/

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> ( <span
class="methodparam"><span class="type">mixed</span> `$class`</span> ,
<span class="methodparam"><span class="type">string</span>
`$name`</span> )

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">string</span> <span
class="methodname">export</span> ( <span class="methodparam"><span
class="type">mixed</span> `$class`</span> , <span
class="methodparam"><span class="type">string</span> `$name`</span> \[,
<span class="methodparam"><span class="type">bool</span>
`$return`</span> \] )

<span class="modifier">public</span> <span
class="type">ReflectionClass</span> <span
class="methodname">getDeclaringClass</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getDocComment</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getModifiers</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getName</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">getValue</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">isPrivate</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">isProtected</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">isPublic</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">\_\_toString</span> ( <span
class="methodparam">void</span> )

}

Properties
----------

`name`  
Name of the class constant. Read-only, throws <span
class="classname">ReflectionException</span> in attempt to write.

`class`  
Name of the class where the class constant is defined. Read-only, throws
<span class="classname">ReflectionException</span> in attempt to write.

ReflectionClassConstant::\_\_construct
======================================

Constructs a ReflectionClassConstant

### Description

<span class="modifier">public</span> <span
class="methodname">ReflectionClassConstant::\_\_construct</span> ( <span
class="methodparam"><span class="type">mixed</span> `$class`</span> ,
<span class="methodparam"><span class="type">string</span>
`$name`</span> )

Constructs a new <span class="classname">ReflectionClassConstant</span>
object.

### Parameters

`class`  
Either a <span class="type">string</span> containing the name of the
class to reflect, or an <span class="type">object</span>.

`name`  
The name of the class constant.

### Return Values

Returns constructed <span
class="classname">ReflectionClassConstant</span> instance.

### Errors/Exceptions

Throws an <span class="classname">Exception</span> in case the given
class constant does not exist.

### See Also

-   <a href="/language/oop5/decon.html#language.oop5.decon.constructor" class="link">Constructors</a>

ReflectionClassConstant::export
===============================

Export

**Warning**

This function has been *DEPRECATED* as of PHP 7.4.0. Relying on this
function is highly discouraged.

### Description

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">string</span> <span
class="methodname">ReflectionClassConstant::export</span> ( <span
class="methodparam"><span class="type">mixed</span> `$class`</span> ,
<span class="methodparam"><span class="type">string</span>
`$name`</span> \[, <span class="methodparam"><span
class="type">bool</span> `$return`</span> \] )

Exports a reflection.

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`class`  
The reflection to export.

`name`  
The class constant name.

`return`  
Setting to **`TRUE`** will return the export, as opposed to emitting it.
Setting to **`FALSE`** (the default) will do the opposite.

### Return Values

### See Also

-   <span
    class="methodname">ReflectionClassConstant::\_\_toString</span>

ReflectionClassConstant::getDeclaringClass
==========================================

Gets declaring class

### Description

<span class="modifier">public</span> <span
class="type">ReflectionClass</span> <span
class="methodname">ReflectionClassConstant::getDeclaringClass</span> (
<span class="methodparam">void</span> )

Gets the declaring class.

### Parameters

This function has no parameters.

### Return Values

A <span class="classname">ReflectionClass</span> object.

ReflectionClassConstant::getDocComment
======================================

Gets doc comments

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">ReflectionClassConstant::getDocComment</span> (
<span class="methodparam">void</span> )

Gets doc comments from a class constant.

### Parameters

This function has no parameters.

### Return Values

The doc comment if it exists, otherwise **`FALSE`**

ReflectionClassConstant::getModifiers
=====================================

Gets the class constant modifiers

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">ReflectionClassConstant::getModifiers</span> ( <span
class="methodparam">void</span> )

Returns a bitfield of the access modifiers for this class constant.

### Parameters

This function has no parameters.

### Return Values

A numeric representation of the modifiers. The actual meanings of these
modifiers are described in the
<a href="/class/reflectionmethod.html#ReflectionMethod%20Modifiers" class="link">predefined constants</a>.

### See Also

-   <span class="methodname">Reflection::getModifierNames</span>

ReflectionClassConstant::getName
================================

Get name of the constant

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">ReflectionClassConstant::getName</span> ( <span
class="methodparam">void</span> )

### Parameters

This function has no parameters.

### Return Values

Returns the constant's name.

ReflectionClassConstant::getValue
=================================

Gets value

### Description

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">ReflectionClassConstant::getValue</span> (
<span class="methodparam">void</span> )

Gets the class constant's value.

### Parameters

This function has no parameters.

### Return Values

The value of the class constant.

ReflectionClassConstant::isPrivate
==================================

Checks if class constant is private

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ReflectionClassConstant::isPrivate</span> (
<span class="methodparam">void</span> )

Checks if the class constant is private.

### Parameters

This function has no parameters.

### Return Values

**`TRUE`** if the class constant is private, otherwise **`FALSE`**

### See Also

-   <span class="methodname">ReflectionClassConstant::isPublic</span>
-   <span class="methodname">ReflectionClassConstant::isProtected</span>

ReflectionClassConstant::isProtected
====================================

Checks if class constant is protected

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ReflectionClassConstant::isProtected</span> (
<span class="methodparam">void</span> )

Checks if the class constant is protected.

### Parameters

This function has no parameters.

### Return Values

**`TRUE`** if the class constant is protected, otherwise **`FALSE`**

### See Also

-   <span class="methodname">ReflectionClassConstant::isPublic</span>
-   <span class="methodname">ReflectionClassConstant::isPrivate</span>

ReflectionClassConstant::isPublic
=================================

Checks if class constant is public

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ReflectionClassConstant::isPublic</span> (
<span class="methodparam">void</span> )

Checks if the class constant is public.

### Parameters

This function has no parameters.

### Return Values

**`TRUE`** if the class constant is public, otherwise **`FALSE`**

### See Also

-   <span class="methodname">ReflectionClassConstant::isPrivate</span>
-   <span class="methodname">ReflectionClassConstant::isProtected</span>

ReflectionClassConstant::\_\_toString
=====================================

Returns the string representation of the ReflectionClassConstant object

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">ReflectionClassConstant::\_\_toString</span> (
<span class="methodparam">void</span> )

Returns the string representation of the ReflectionClassConstant object.

### Parameters

This function has no parameters.

### Return Values

A string representation of this <span
class="classname">ReflectionClassConstant</span> instance.

### See Also

-   <span class="methodname">ReflectionClassConstant::export</span>
-   <a href="/language/oop5/magic.html#object.tostring" class="link">__toString()</a>

Introduction
------------

Class synopsis
--------------

**ReflectionZendExtension**

<span class="ooclass"> class **ReflectionZendExtension** </span> <span
class="oointerface">implements <span
class="interfacename">Reflector</span> </span> {

/\* Properties \*/

<span class="modifier">public</span> `$name` ;

/\* Methods \*/

<span class="modifier">final</span> <span
class="modifier">private</span> <span class="type">void</span> <span
class="methodname">\_\_clone</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> )

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">string</span> <span
class="methodname">export</span> ( <span class="methodparam"><span
class="type">string</span> `$name`</span> \[, <span
class="methodparam"><span class="type">bool</span> `$return`</span> \] )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getAuthor</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getCopyright</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getName</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getURL</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getVersion</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">\_\_toString</span> ( <span
class="methodparam">void</span> )

}

Properties
----------

`name`  
Name of the extension. Read-only, throws <span
class="classname">ReflectionException</span> in attempt to write.

ReflectionZendExtension::\_\_clone
==================================

Clone handler

### Description

<span class="modifier">final</span> <span
class="modifier">private</span> <span class="type">void</span> <span
class="methodname">ReflectionZendExtension::\_\_clone</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

ReflectionZendExtension::\_\_construct
======================================

Constructor

### Description

<span class="modifier">public</span> <span
class="methodname">ReflectionZendExtension::\_\_construct</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`name`  

### Return Values

ReflectionZendExtension::export
===============================

Export

**Warning**

This function has been *DEPRECATED* as of PHP 7.4.0. Relying on this
function is highly discouraged.

### Description

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">string</span> <span
class="methodname">ReflectionZendExtension::export</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> \[,
<span class="methodparam"><span class="type">bool</span>
`$return`</span> \] )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`name`  

`return`  

### Return Values

### See Also

-   <span
    class="methodname">ReflectionClassConstant::\_\_toString</span>

ReflectionZendExtension::getAuthor
==================================

Gets author

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">ReflectionZendExtension::getAuthor</span> (
<span class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

ReflectionZendExtension::getCopyright
=====================================

Gets copyright

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">ReflectionZendExtension::getCopyright</span> (
<span class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

ReflectionZendExtension::getName
================================

Gets name

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">ReflectionZendExtension::getName</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

ReflectionZendExtension::getURL
===============================

Gets URL

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">ReflectionZendExtension::getURL</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

ReflectionZendExtension::getVersion
===================================

Gets version

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">ReflectionZendExtension::getVersion</span> (
<span class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

ReflectionZendExtension::\_\_toString
=====================================

To string handler

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">ReflectionZendExtension::\_\_toString</span> (
<span class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

Introduction
------------

The <span class="classname">ReflectionExtension</span> class reports
information about an extension.

Class synopsis
--------------

**ReflectionExtension**

<span class="ooclass"> class **ReflectionExtension** </span> <span
class="oointerface">implements <span
class="interfacename">Reflector</span> </span> {

/\* Properties \*/

<span class="modifier">public</span> `$name` ;

/\* Methods \*/

<span class="modifier">final</span> <span
class="modifier">private</span> <span class="type">void</span> <span
class="methodname">\_\_clone</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> )

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">string</span> <span
class="methodname">export</span> ( <span class="methodparam"><span
class="type">string</span> `$name`</span> \[, <span
class="methodparam"><span class="type">string</span> `$return`<span
class="initializer"> = **`FALSE`**</span></span> \] )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">getClasses</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">getClassNames</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">getConstants</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">getDependencies</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">getFunctions</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">getINIEntries</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getName</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getVersion</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">info</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">isPersistent</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">isTemporary</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">\_\_toString</span> ( <span
class="methodparam">void</span> )

}

Properties
----------

`name`  
Name of the extension, same as calling the <span
class="methodname">ReflectionExtension::getName</span> method.

ReflectionExtension::\_\_clone
==============================

Clones

### Description

<span class="modifier">final</span> <span
class="modifier">private</span> <span class="type">void</span> <span
class="methodname">ReflectionExtension::\_\_clone</span> ( <span
class="methodparam">void</span> )

The clone method prevents an object from being cloned. Reflection
objects cannot be cloned.

### Parameters

This function has no parameters.

### Return Values

No value is returned, if called a fatal error will occur.

### See Also

-   <span class="methodname">ReflectionExtension::\_\_construct</span>
-   <a href="/language/oop5/cloning.html" class="link">Object cloning</a>

ReflectionExtension::\_\_construct
==================================

Constructs a ReflectionExtension

### Description

<span class="modifier">public</span> <span
class="methodname">ReflectionExtension::\_\_construct</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> )

Construct a <span class="classname">ReflectionExtension</span> <span
class="type">object</span>.

### Parameters

`name`  
Name of the extension.

### Return Values

A <span class="classname">ReflectionExtension</span> <span
class="type">object</span>.

### Examples

**Example \#1 <span class="classname">ReflectionExtension</span>
example**

``` php
<?php
$ext = new ReflectionExtension('Reflection');

printf('Extension: %s (version: %s)', $ext->getName(), $ext->getVersion());
?>
```

The above example will output something similar to:

    Extension: Reflection (version: $Revision: 330543 $)

### See Also

-   <span class="methodname">ReflectionExtension::info</span>
-   <a href="/language/oop5/decon.html#language.oop5.decon.constructor" class="link">Constructors</a>

ReflectionExtension::export
===========================

Export

**Warning**

This function has been *DEPRECATED* as of PHP 7.4.0. Relying on this
function is highly discouraged.

### Description

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">string</span> <span
class="methodname">ReflectionExtension::export</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> \[,
<span class="methodparam"><span class="type">string</span>
`$return`<span class="initializer"> = **`FALSE`**</span></span> \] )

Exports a reflected extension. The output format of this function is the
same as the CLI argument *--re \[extension\]*.

### Parameters

`name`  
The reflection to export.

`return`  
Setting to **`TRUE`** will return the export, as opposed to emitting it.
Setting to **`FALSE`** (the default) will do the opposite.

### Return Values

If the `return` parameter is set to **`TRUE`**, then the export is
returned as a <span class="type">string</span>, otherwise **`NULL`** is
returned.

### See Also

-   <span class="methodname">ReflectionExtension::info</span>
-   <span class="methodname">ReflectionExtension::\_\_toString</span>

ReflectionExtension::getClasses
===============================

Gets classes

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">ReflectionExtension::getClasses</span> ( <span
class="methodparam">void</span> )

Gets a list of classes from an extension.

### Parameters

This function has no parameters.

### Return Values

An array of <span class="classname">ReflectionClass</span> objects, one
for each class within the extension. If no classes are defined, an empty
array is returned.

### Examples

**Example \#1 <span
class="methodname">ReflectionExtension::getClasses</span> example**

``` php
<?php
$ext = new ReflectionExtension('XMLWriter');
var_dump($ext->getClasses());
?>
```

The above example will output something similar to:

    array(1) {
      ["XMLWriter"]=>
      &object(ReflectionClass)#2 (1) {
        ["name"]=>
        string(9) "XMLWriter"
      }
    }

### See Also

-   <span class="methodname">ReflectionExtension::getClassNames</span>

ReflectionExtension::getClassNames
==================================

Gets class names

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">ReflectionExtension::getClassNames</span> (
<span class="methodparam">void</span> )

Gets a listing of class names as defined in the extension.

### Parameters

This function has no parameters.

### Return Values

An <span class="type">array</span> of class names, as defined in the
extension. If no classes are defined, an empty array is returned.

### Examples

**Example \#1 <span
class="methodname">ReflectionExtension::getClassNames</span> example**

``` php
<?php
$ext = new ReflectionExtension('XMLWriter');
var_dump($ext->getClassNames());
?>
```

The above example will output something similar to:

    array(1) {
      [0]=>
      string(9) "XMLWriter"
    }

### See Also

-   <span class="methodname">ReflectionExtension::getClasses</span>
-   <span class="methodname">ReflectionExtension::getName</span>

ReflectionExtension::getConstants
=================================

Gets constants

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">ReflectionExtension::getConstants</span> (
<span class="methodparam">void</span> )

Get defined constants from an extension.

### Parameters

This function has no parameters.

### Return Values

An associative array with constant names as keys.

### Examples

**Example \#1 <span
class="methodname">ReflectionExtension::getConstants</span> example**

``` php
<?php
$ext = new ReflectionExtension('DOM');

print_r($ext->getConstants());
?>
```

The above example will output something similar to:

    Array
    (
        [XML_ELEMENT_NODE] => 1
        [XML_ATTRIBUTE_NODE] => 2
        [XML_TEXT_NODE] => 3
        [XML_CDATA_SECTION_NODE] => 4
        [XML_ENTITY_REF_NODE] => 5
        [XML_ENTITY_NODE] => 6
        [XML_PI_NODE] => 7
        [XML_COMMENT_NODE] => 8
        [XML_DOCUMENT_NODE] => 9
        [XML_DOCUMENT_TYPE_NODE] => 10
        [XML_DOCUMENT_FRAG_NODE] => 11
        [XML_NOTATION_NODE] => 12
        [XML_HTML_DOCUMENT_NODE] => 13
        [XML_DTD_NODE] => 14
        [XML_ELEMENT_DECL_NODE] => 15
        [XML_ATTRIBUTE_DECL_NODE] => 16
        [XML_ENTITY_DECL_NODE] => 17
        [XML_NAMESPACE_DECL_NODE] => 18
        [XML_LOCAL_NAMESPACE] => 18
        [XML_ATTRIBUTE_CDATA] => 1
        [XML_ATTRIBUTE_ID] => 2
        [XML_ATTRIBUTE_IDREF] => 3
        [XML_ATTRIBUTE_IDREFS] => 4
        [XML_ATTRIBUTE_ENTITY] => 6
        [XML_ATTRIBUTE_NMTOKEN] => 7
        [XML_ATTRIBUTE_NMTOKENS] => 8
        [XML_ATTRIBUTE_ENUMERATION] => 9
        [XML_ATTRIBUTE_NOTATION] => 10
        [DOM_PHP_ERR] => 0
        [DOM_INDEX_SIZE_ERR] => 1
        [DOMSTRING_SIZE_ERR] => 2
        [DOM_HIERARCHY_REQUEST_ERR] => 3
        [DOM_WRONG_DOCUMENT_ERR] => 4
        [DOM_INVALID_CHARACTER_ERR] => 5
        [DOM_NO_DATA_ALLOWED_ERR] => 6
        [DOM_NO_MODIFICATION_ALLOWED_ERR] => 7
        [DOM_NOT_FOUND_ERR] => 8
        [DOM_NOT_SUPPORTED_ERR] => 9
        [DOM_INUSE_ATTRIBUTE_ERR] => 10
        [DOM_INVALID_STATE_ERR] => 11
        [DOM_SYNTAX_ERR] => 12
        [DOM_INVALID_MODIFICATION_ERR] => 13
        [DOM_NAMESPACE_ERR] => 14
        [DOM_INVALID_ACCESS_ERR] => 15
        [DOM_VALIDATION_ERR] => 16
    )

### See Also

-   <span class="methodname">ReflectionExtension::getINIEntries</span>

ReflectionExtension::getDependencies
====================================

Gets dependencies

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">ReflectionExtension::getDependencies</span> (
<span class="methodparam">void</span> )

Gets dependencies, by listing both required and conflicting
dependencies.

### Parameters

This function has no parameters.

### Return Values

An associative <span class="type">array</span> with dependencies as keys
and either *Required*, *Optional* or *Conflicts* as the values.

### Examples

**Example \#1 <span
class="methodname">ReflectionExtension::getDependencies</span> example**

``` php
<?php
$dom = new ReflectionExtension('dom');

print_r($dom->getDependencies());
?>
```

The above example will output something similar to:

    Array
    (
        [libxml] => Required
        [domxml] => Conflicts
    )

### See Also

-   <span class="methodname">ReflectionClass::getVersion</span>

ReflectionExtension::getFunctions
=================================

Gets extension functions

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">ReflectionExtension::getFunctions</span> (
<span class="methodparam">void</span> )

Get defined functions from an extension.

### Parameters

This function has no parameters.

### Return Values

An associative array of <span
class="classname">ReflectionFunction</span> objects, for each function
defined in the extension with the keys being the function names. If no
function are defined, an empty array is returned.

### Examples

**Example \#1 <span
class="methodname">ReflectionExtension::getFunctions</span> example**

``` php
<?php
$dom = new ReflectionExtension('SimpleXML');

print_r($dom->getFunctions());
?>
```

The above example will output something similar to:

    Array
    (
        [simplexml_load_file] => ReflectionFunction Object
            (
                [name] => simplexml_load_file
            )

        [simplexml_load_string] => ReflectionFunction Object
            (
                [name] => simplexml_load_string
            )

        [simplexml_import_dom] => ReflectionFunction Object
            (
                [name] => simplexml_import_dom
            )

    )

### See Also

-   <span class="methodname">ReflectionExtension::getClasses</span>
-   <span class="function">get\_extension\_funcs</span>

ReflectionExtension::getINIEntries
==================================

Gets extension ini entries

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">ReflectionExtension::getINIEntries</span> (
<span class="methodparam">void</span> )

Get the ini entries for an extension.

### Parameters

This function has no parameters.

### Return Values

An associative <span class="type">array</span> with the ini entries as
keys, with their defined values as values.

### Examples

**Example \#1 <span
class="methodname">ReflectionExtension::getINIEntries</span> example**

``` php
<?php
$ext = new ReflectionExtension('mysql');

print_r($ext->getINIEntries());
?>
```

The above example will output something similar to:

    Array
    (
        [mysql.allow_persistent] => 1
        [mysql.max_persistent] => -1
        [mysql.max_links] => -1
        [mysql.default_host] => 
        [mysql.default_user] => 
        [mysql.default_password] => 
        [mysql.default_port] => 
        [mysql.default_socket] => 
        [mysql.connect_timeout] => 60
        [mysql.trace_mode] => 
        [mysql.allow_local_infile] => 1
        [mysql.cache_size] => 2000
    )

### See Also

-   <span class="function">ini\_get\_all</span>
-   <span class="methodname">ReflectionExtension::getConstants</span>

ReflectionExtension::getName
============================

Gets extension name

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">ReflectionExtension::getName</span> ( <span
class="methodparam">void</span> )

Gets the extensions name.

### Parameters

This function has no parameters.

### Return Values

The extensions name.

### Examples

**Example \#1 <span
class="methodname">ReflectionExtension::getName</span> example**

``` php
<?php
$ext = new ReflectionExtension('mysqli');
var_dump($ext->getName());
?>
```

The above example will output something similar to:

    string(6) "mysqli"

### See Also

-   <span class="methodname">ReflectionExtension::getClassNames</span>

ReflectionExtension::getVersion
===============================

Gets extension version

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">ReflectionExtension::getVersion</span> ( <span
class="methodparam">void</span> )

Gets the version of the extension.

### Parameters

This function has no parameters.

### Return Values

The version of the extension.

### Examples

**Example \#1 <span
class="methodname">ReflectionExtension::getVersion</span> example**

``` php
<?php
$ext = new ReflectionExtension('mysqli');
var_dump($ext->getVersion());
?>
```

The above example will output something similar to:

    string(3) "0.1"

### See Also

-   <span class="methodname">ReflectionExtension::info</span>

ReflectionExtension::info
=========================

Print extension info

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">ReflectionExtension::info</span> ( <span
class="methodparam">void</span> )

Prints out the "<span class="function">phpinfo</span>" snippet for the
given extension.

### Parameters

This function has no parameters.

### Return Values

Information about the extension.

### Examples

**Example \#1 <span class="methodname">ReflectionExtension::info</span>
example**

``` php
<?php
$ext = new ReflectionExtension('mysqli');
$ext->info();
?>
```

The above example will output something similar to:

    mysqli

    MysqlI Support => enabled
    Client API library version => mysqlnd 5.0.5-dev - 081106 - $Revision: 315808 $
    Active Persistent Links => 0
    Inactive Persistent Links => 0
    Active Links => 0
    Persistent cache => enabled
    put_hits => 0
    put_misses => 0
    get_hits => 0
    get_misses => 0
    size => 2000
    free_items => 2000
    references => 2

    Directive => Local Value => Master Value
    mysqli.max_links => Unlimited => Unlimited
    mysqli.max_persistent => Unlimited => Unlimited
    mysqli.allow_persistent => On => On
    mysqli.default_host => no value => no value
    mysqli.default_user => no value => no value
    mysqli.default_pw => no value => no value
    mysqli.default_port => 3306 => 3306
    mysqli.default_socket => no value => no value
    mysqli.reconnect => Off => Off
    mysqli.allow_local_infile => On => On
    mysqli.cache_size => 2000 => 2000

### See Also

-   <span class="methodname">ReflectionExtension::getName</span>
-   <span class="function">phpinfo</span>

ReflectionExtension::isPersistent
=================================

Returns whether this extension is persistent

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">ReflectionExtension::isPersistent</span> (
<span class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

Returns **`TRUE`** for extensions loaded by
<a href="/ini/core.html#ini.extension" class="link"><em>extension</em></a>,
**`FALSE`** otherwise.

### See Also

-   <span class="methodname">ReflectionExtension::isTemporary</span>

ReflectionExtension::isTemporary
================================

Returns whether this extension is temporary

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">ReflectionExtension::isTemporary</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

Returns **`TRUE`** for extensions loaded by <span
class="function">dl</span>, **`FALSE`** otherwise.

### See Also

-   <span class="methodname">ReflectionExtension::isPersistent</span>

ReflectionExtension::\_\_toString
=================================

To string

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">ReflectionExtension::\_\_toString</span> (
<span class="methodparam">void</span> )

Exports a reflected extension and returns it as a <span
class="type">string</span>. This is the same as the <span
class="methodname">ReflectionExtension::export</span> with the `return`
set to **`TRUE`**.

### Parameters

This function has no parameters.

### Return Values

Returns the exported extension as a string, in the same way as the <span
class="methodname">ReflectionExtension::export</span>.

### See Also

-   <span class="methodname">ReflectionExtension::\_\_construct</span>
-   <span class="methodname">ReflectionExtension::export</span>
-   <a href="/language/oop5/magic.html#object.tostring" class="link">__toString()</a>

Introduction
------------

The <span class="classname">ReflectionFunction</span> class reports
information about a function.

Class synopsis
--------------

**ReflectionFunction**

<span class="ooclass"> class **ReflectionFunction** </span> <span
class="ooclass"> <span class="modifier">extends</span>
**ReflectionFunctionAbstract** </span> <span
class="oointerface">implements <span
class="interfacename">Reflector</span> </span> {

/\* Constants \*/

<span class="modifier">const</span> <span class="type">int</span>
`ReflectionFunction::IS_DEPRECATED` <span class="initializer"> =
262144</span> ;

/\* Properties \*/

<span class="modifier">public</span> `$name` ;

/\* Methods \*/

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> ( <span
class="methodparam"><span class="type">mixed</span> `$name`</span> )

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">string</span> <span
class="methodname">export</span> ( <span class="methodparam"><span
class="type">string</span> `$name`</span> \[, <span
class="methodparam"><span class="type">string</span> `$return`</span> \]
)

<span class="modifier">public</span> <span class="type">Closure</span>
<span class="methodname">getClosure</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">invoke</span> ( <span class="methodparam"><span
class="type">mixed</span> `$args`</span> )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">invokeArgs</span> ( <span
class="methodparam"><span class="type">array</span> `$args`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">isDisabled</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">\_\_toString</span> ( <span
class="methodparam">void</span> )

/\* Inherited methods \*/

<span class="modifier">final</span> <span
class="modifier">private</span> <span class="type">void</span> <span
class="methodname">ReflectionFunctionAbstract::\_\_clone</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="type">ReflectionClass</span> <span
class="methodname">ReflectionFunctionAbstract::getClosureScopeClass</span>
( <span class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">object</span>
<span
class="methodname">ReflectionFunctionAbstract::getClosureThis</span> (
<span class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span
class="methodname">ReflectionFunctionAbstract::getDocComment</span> (
<span class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">ReflectionFunctionAbstract::getEndLine</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="type">ReflectionExtension</span> <span
class="methodname">ReflectionFunctionAbstract::getExtension</span> (
<span class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span
class="methodname">ReflectionFunctionAbstract::getExtensionName</span> (
<span class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">ReflectionFunctionAbstract::getFileName</span>
( <span class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">ReflectionFunctionAbstract::getName</span> (
<span class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span
class="methodname">ReflectionFunctionAbstract::getNamespaceName</span> (
<span class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">ReflectionFunctionAbstract::getNumberOfParameters</span>
( <span class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">ReflectionFunctionAbstract::getNumberOfRequiredParameters</span>
( <span class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span
class="methodname">ReflectionFunctionAbstract::getParameters</span> (
<span class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="type">ReflectionType</span> <span
class="methodname">ReflectionFunctionAbstract::getReturnType</span> (
<span class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">ReflectionFunctionAbstract::getShortName</span>
( <span class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">ReflectionFunctionAbstract::getStartLine</span> (
<span class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span
class="methodname">ReflectionFunctionAbstract::getStaticVariables</span>
( <span class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span
class="methodname">ReflectionFunctionAbstract::hasReturnType</span> (
<span class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ReflectionFunctionAbstract::inNamespace</span>
( <span class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ReflectionFunctionAbstract::isClosure</span> (
<span class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ReflectionFunctionAbstract::isDeprecated</span>
( <span class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ReflectionFunctionAbstract::isGenerator</span>
( <span class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ReflectionFunctionAbstract::isInternal</span> (
<span class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span
class="methodname">ReflectionFunctionAbstract::isUserDefined</span> (
<span class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ReflectionFunctionAbstract::isVariadic</span> (
<span class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span
class="methodname">ReflectionFunctionAbstract::returnsReference</span> (
<span class="methodparam">void</span> )

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type">void</span> <span
class="methodname">ReflectionFunctionAbstract::\_\_toString</span> (
<span class="methodparam">void</span> )

}

Properties
----------

`name`  
Name of the function. Read-only, throws <span
class="classname">ReflectionException</span> in attempt to write.

Predefined Constants
--------------------

ReflectionFunction Modifiers
----------------------------

**`ReflectionFunction::IS_DEPRECATED`**  
Indicates deprecated functions.

ReflectionFunction::\_\_construct
=================================

Constructs a ReflectionFunction object

### Description

<span class="modifier">public</span> <span
class="methodname">ReflectionFunction::\_\_construct</span> ( <span
class="methodparam"><span class="type">mixed</span> `$name`</span> )

Constructs a <span class="classname">ReflectionFunction</span> object.

### Parameters

`name`  
The name of the function to reflect or a
<a href="/functions/anonymous.html" class="link">closure</a>.

### Return Values

No value is returned.

### Errors/Exceptions

A <span class="classname">ReflectionException</span> if the `name`
parameter does not contain a valid function.

### Examples

**Example \#1 <span
class="methodname">ReflectionFunction::\_\_construct</span> example**

``` php
<?php
/**
 * A simple counter
 *
 * @return    int
 */
function counter1()
{
    static $c = 0;
    return ++$c;
}

/**
 * Another simple counter
 *
 * @return    int
 */
$counter2 = function()
{
    static $d = 0;
    return ++$d;

};

function dumpReflectionFunction($func)
{
    // Print out basic information
    printf(
        "\n\n===> The %s function '%s'\n".
        "     declared in %s\n".
        "     lines %d to %d\n",
        $func->isInternal() ? 'internal' : 'user-defined',
        $func->getName(),
        $func->getFileName(),
        $func->getStartLine(),
        $func->getEndline()
    );

    // Print documentation comment
    printf("---> Documentation:\n %s\n", var_export($func->getDocComment(), 1));

    // Print static variables if existant
    if ($statics = $func->getStaticVariables())
    {
        printf("---> Static variables: %s\n", var_export($statics, 1));
    }
}

// Create an instance of the ReflectionFunction class
dumpReflectionFunction(new ReflectionFunction('counter1'));
dumpReflectionFunction(new ReflectionFunction($counter2));
?>
```

The above example will output something similar to:

    ===> The user-defined function 'counter1'
         declared in Z:\reflectcounter.php
         lines 7 to 11
    ---> Documentation:
     '/**
     * A simple counter
     *
     * @return    int
     */'
    ---> Static variables: array (
      'c' => 0,
    )


    ===> The user-defined function '{closure}'
         declared in Z:\reflectcounter.php
         lines 18 to 23
    ---> Documentation:
     '/**
     * Another simple counter
     *
     * @return    int
     */'
    ---> Static variables: array (
      'd' => 0,
    )

### See Also

-   <span class="methodname">ReflectionMethod::\_\_construct</span>
-   <a href="/language/oop5/decon.html#language.oop5.decon.constructor" class="link">Constructors</a>

ReflectionFunction::export
==========================

Exports function

**Warning**

This function has been *DEPRECATED* as of PHP 7.4.0. Relying on this
function is highly discouraged.

### Description

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">string</span> <span
class="methodname">ReflectionFunction::export</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> \[,
<span class="methodparam"><span class="type">string</span>
`$return`</span> \] )

Exports a Reflected function.

### Parameters

`name`  
The reflection to export.

`return`  
Setting to **`TRUE`** will return the export, as opposed to emitting it.
Setting to **`FALSE`** (the default) will do the opposite.

### Return Values

If the `return` parameter is set to **`TRUE`**, then the export is
returned as a <span class="type">string</span>, otherwise **`NULL`** is
returned.

### See Also

-   <span class="methodname">ReflectionFunction::invoke</span>
-   <span class="methodname">ReflectionFunction::\_\_toString</span>

ReflectionFunction::getClosure
==============================

Returns a dynamically created closure for the function

### Description

<span class="modifier">public</span> <span class="type">Closure</span>
<span class="methodname">ReflectionFunction::getClosure</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

Returns <span class="classname">Closure</span>. Returns **`NULL`** in
case of an error.

ReflectionFunction::invoke
==========================

Invokes function

### Description

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">ReflectionFunction::invoke</span> ( <span
class="methodparam"><span class="type">mixed</span> `$args`</span> )

Invokes a reflected function.

### Parameters

`args`  
The passed in argument list. It accepts a variable number of arguments
which are passed to the function much like <span
class="function">call\_user\_func</span> is.

### Return Values

Returns the result of the invoked function call.

### Examples

**Example \#1 <span class="methodname">ReflectionFunction::invoke</span>
example**

``` php
<?php
function title($title, $name)
{
    return sprintf("%s. %s\r\n", $title, $name);
}

$function = new ReflectionFunction('title');

echo $function->invoke('Dr', 'Phil');
?>
```

The above example will output:

    Dr. Phil

### Notes

> **Note**:
>
> If the function has arguments that need to be references, then they
> must be references in the passed argument list.

### See Also

-   <span class="methodname">ReflectionFunction::export</span>
-   <a href="/language/oop5/magic.html#object.invoke" class="link">__invoke()</a>
-   <span class="function">call\_user\_func</span>

ReflectionFunction::invokeArgs
==============================

Invokes function args

### Description

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">ReflectionFunction::invokeArgs</span> ( <span
class="methodparam"><span class="type">array</span> `$args`</span> )

Invokes the function and pass its arguments as array.

### Parameters

`args`  
The passed arguments to the function as an array, much like <span
class="function">call\_user\_func\_array</span> works.

### Return Values

Returns the result of the invoked function

### Examples

**Example \#1 <span
class="methodname">ReflectionFunction::invokeArgs</span> example**

``` php
<?php
function title($title, $name)
{
    return sprintf("%s. %s\r\n", $title, $name);
}

$function = new ReflectionFunction('title');

echo $function->invokeArgs(array('Dr', 'Phil'));
?>
```

The above example will output:

    Dr. Phil

**Example \#2 <span
class="methodname">ReflectionFunction::invokeArgs</span> with references
example**

``` php
<?php
function get_false_conditions(array $conditions, array &$false_conditions)
{
    foreach ($conditions as $condition) {
        if (!$condition) {
            $false_conditions[] = $condition;
        }
    }
}

$function_ref     = new ReflectionFunction('get_false_conditions');

$conditions       = array(true, false, -1, 0, 1);
$false_conditions = array();

$function_ref->invokeArgs(array($conditions, &$false_conditions));

var_dump($false_conditions);
?>
```

The above example will output:

    array(2) {
      [0]=>
      bool(false)
      [1]=>
      int(0)
    }

### Notes

> **Note**:
>
> If the function has arguments that need to be references, then they
> must be references in the passed argument list.

### See Also

-   <span class="methodname">ReflectionFunction::invoke</span>
-   <span
    class="methodname">ReflectionFunctionAbstract::getNumberOfParameters</span>
-   <a href="/language/oop5/magic.html#object.invoke" class="link">__invoke()</a>
-   <span class="function">call\_user\_func\_array</span>

ReflectionFunction::isDisabled
==============================

Checks if function is disabled

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ReflectionFunction::isDisabled</span> ( <span
class="methodparam">void</span> )

Checks if the function is disabled, via the
<a href="/ini/core.html#ini.disable-functions" class="link">disable_functions</a>
directive.

### Parameters

This function has no parameters.

### Return Values

**`TRUE`** if it's disable, otherwise **`FALSE`**

### See Also

-   <span
    class="methodname">ReflectionFunctionAbstract::isUserDefined</span>
-   <a href="/ini/core.html#ini.disable-functions" class="link">disable_functions directive</a>

ReflectionFunction::\_\_toString
================================

To string

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">ReflectionFunction::\_\_toString</span> ( <span
class="methodparam">void</span> )

To string.

### Parameters

This function has no parameters.

### Return Values

Returns <span class="methodname">ReflectionFunction::export</span>-like
output for the function.

### Examples

**Example \#1 <span
class="methodname">ReflectionFunction::\_\_toString</span> example**

``` php
<?php
function title($title, $name)
{
    return sprintf("%s. %s\r\n", $title, $name);
}

echo new ReflectionFunction('title');
?>
```

The above example will output something similar to:

    Function [ <user> function title ] {
      @@ Command line code 1 - 1

      - Parameters [2] {
        Parameter #0 [ <required> $title ]
        Parameter #1 [ <required> $name ]
      }
    }

### See Also

-   <span class="methodname">ReflectionFunction::export</span>
-   <span class="methodname">ReflectionClass::clone</span>
-   <a href="/language/oop5/magic.html#object.tostring" class="link">__toString()</a>

Introduction
------------

A parent class to <span class="classname">ReflectionFunction</span>,
read its description for details.

Class synopsis
--------------

**ReflectionFunctionAbstract**

<span class="ooclass"> class **ReflectionFunctionAbstract** </span>
<span class="oointerface">implements <span
class="interfacename">Reflector</span> </span> {

/\* Properties \*/

<span class="modifier">public</span> `$name` ;

/\* Methods \*/

<span class="modifier">final</span> <span
class="modifier">private</span> <span class="type">void</span> <span
class="methodname">\_\_clone</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="type">ReflectionClass</span> <span
class="methodname">getClosureScopeClass</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">object</span>
<span class="methodname">getClosureThis</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getDocComment</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getEndLine</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="type">ReflectionExtension</span> <span
class="methodname">getExtension</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getExtensionName</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getFileName</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getName</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getNamespaceName</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getNumberOfParameters</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getNumberOfRequiredParameters</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">getParameters</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="type">ReflectionType</span> <span
class="methodname">getReturnType</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getShortName</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getStartLine</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">getStaticVariables</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">hasReturnType</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">inNamespace</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">isClosure</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">isDeprecated</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">isGenerator</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">isInternal</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">isUserDefined</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">isVariadic</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">returnsReference</span> ( <span
class="methodparam">void</span> )

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type">void</span> <span
class="methodname">\_\_toString</span> ( <span
class="methodparam">void</span> )

}

Properties
----------

`name`  
Name of the function. Read-only, throws <span
class="classname">ReflectionException</span> in attempt to write.

ReflectionFunctionAbstract::\_\_clone
=====================================

Clones function

### Description

<span class="modifier">final</span> <span
class="modifier">private</span> <span class="type">void</span> <span
class="methodname">ReflectionFunctionAbstract::\_\_clone</span> ( <span
class="methodparam">void</span> )

Clones a function.

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

### See Also

-   <a href="/language/oop5/cloning.html" class="link">Object cloning</a>

ReflectionFunctionAbstract::getClosureScopeClass
================================================

Returns the scope associated to the closure

### Description

<span class="modifier">public</span> <span
class="type">ReflectionClass</span> <span
class="methodname">ReflectionFunctionAbstract::getClosureScopeClass</span>
( <span class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

Returns the class on success or **`NULL`** on failure.

ReflectionFunctionAbstract::getClosureThis
==========================================

Returns this pointer bound to closure

### Description

<span class="modifier">public</span> <span class="type">object</span>
<span
class="methodname">ReflectionFunctionAbstract::getClosureThis</span> (
<span class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

Returns `$this` pointer. Returns **`NULL`** in case of an error.

ReflectionFunctionAbstract::getDocComment
=========================================

Gets doc comment

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span
class="methodname">ReflectionFunctionAbstract::getDocComment</span> (
<span class="methodparam">void</span> )

Get a Doc comment from a function.

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

The doc comment if it exists, otherwise **`FALSE`**

### See Also

-   <span
    class="methodname">ReflectionFunctionAbstract::getStartLine</span>

ReflectionFunctionAbstract::getEndLine
======================================

Gets end line number

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">ReflectionFunctionAbstract::getEndLine</span> ( <span
class="methodparam">void</span> )

Get the ending line number.

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

The ending line number of the user defined function, or **`FALSE`** if
unknown.

### See Also

-   <span
    class="methodname">ReflectionFunctionAbstract::getStartLine</span>

ReflectionFunctionAbstract::getExtension
========================================

Gets extension info

### Description

<span class="modifier">public</span> <span
class="type">ReflectionExtension</span> <span
class="methodname">ReflectionFunctionAbstract::getExtension</span> (
<span class="methodparam">void</span> )

Get the extension information of a function.

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

The extension information, as a <span
class="classname">ReflectionExtension</span> object.

### See Also

-   <span
    class="methodname">ReflectionFunctionAbstract::getExtensionName</span>

ReflectionFunctionAbstract::getExtensionName
============================================

Gets extension name

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span
class="methodname">ReflectionFunctionAbstract::getExtensionName</span> (
<span class="methodparam">void</span> )

Get the extensions name.

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

The extensions name.

### See Also

-   <span
    class="methodname">ReflectionFunctionAbstract::getExtension</span>

ReflectionFunctionAbstract::getFileName
=======================================

Gets file name

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">ReflectionFunctionAbstract::getFileName</span>
( <span class="methodparam">void</span> )

Gets the file name from a user-defined function.

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

The file name.

### See Also

-   <span
    class="methodname">ReflectionFunctionAbstract::getNamespaceName</span>

ReflectionFunctionAbstract::getName
===================================

Gets function name

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">ReflectionFunctionAbstract::getName</span> (
<span class="methodparam">void</span> )

Get the name of the function.

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

The name of the function.

### See Also

-   <span
    class="methodname">ReflectionFunctionAbstract::getExtensionName</span>
-   <span
    class="methodname">ReflectionFunctionAbstract::isUserDefined</span>

ReflectionFunctionAbstract::getNamespaceName
============================================

Gets namespace name

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span
class="methodname">ReflectionFunctionAbstract::getNamespaceName</span> (
<span class="methodparam">void</span> )

Get the namespace name where the class is defined.

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

The namespace name.

### See Also

-   <span
    class="methodname">ReflectionFunctionAbstract::getFileName</span>
-   <a href="/language/namespaces.html" class="link">namespaces</a>

ReflectionFunctionAbstract::getNumberOfParameters
=================================================

Gets number of parameters

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">ReflectionFunctionAbstract::getNumberOfParameters</span>
( <span class="methodparam">void</span> )

Get the number of parameters that a function defines, both optional and
required.

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

The number of parameters.

### See Also

-   <span
    class="methodname">ReflectionFunctionAbstract::getNumberOfRequiredParameters</span>
-   <span class="function">func\_num\_args</span>

ReflectionFunctionAbstract::getNumberOfRequiredParameters
=========================================================

Gets number of required parameters

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">ReflectionFunctionAbstract::getNumberOfRequiredParameters</span>
( <span class="methodparam">void</span> )

Get the number of required parameters that a function defines.

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

The number of required parameters.

### See Also

-   <span
    class="methodname">ReflectionFunctionAbstract::getNumberOfParameters</span>

ReflectionFunctionAbstract::getParameters
=========================================

Gets parameters

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span
class="methodname">ReflectionFunctionAbstract::getParameters</span> (
<span class="methodparam">void</span> )

Get the parameters as an array of <span
class="type">ReflectionParameter</span>.

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

The parameters, as a <span class="classname">ReflectionParameter</span>
object.

### See Also

-   <span
    class="methodname">ReflectionFunctionAbstract::getNumberOfParameters</span>
-   <span class="function">func\_get\_args</span>

ReflectionFunctionAbstract::getReturnType
=========================================

Gets the specified return type of a function

### Description

<span class="modifier">public</span> <span
class="type">ReflectionType</span> <span
class="methodname">ReflectionFunctionAbstract::getReturnType</span> (
<span class="methodparam">void</span> )

Gets the specified return type of a reflected function.

### Parameters

This function has no parameters.

### Return Values

Returns a <span class="classname">ReflectionType</span> object if a
return type is specified, **`NULL`** otherwise.

### Examples

**Example \#1 <span
class="methodname">ReflectionFunctionAbstract::getReturnType</span>
example**

``` php
<?php

function to_int($param) : int {
    return (int) $param;
}

$reflection1 = new ReflectionFunction('to_int');
echo $reflection1->getReturnType();
```

The above example will output:

    int

**Example \#2 Usage on built-in functions**

``` php
<?php

$reflection2 = new ReflectionFunction('array_merge');

var_dump($reflection2->getReturnType());
```

The above example will output:

    null

This is because many internal functions do not have types specified for
their parameters or return values. It is therefore best to avoid using
this method on built-in functions.

### See Also

-   <span
    class="methodname">ReflectionFunctionAbstract::hasReturnType</span>
-   <span class="methodname">ReflectionType::\_\_toString</span>

ReflectionFunctionAbstract::getShortName
========================================

Gets function short name

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">ReflectionFunctionAbstract::getShortName</span>
( <span class="methodparam">void</span> )

Get the short name of the function (without the namespace part).

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

The short name of the function.

### See Also

-   <span
    class="methodname">ReflectionFunctionAbstract::getNamespaceName</span>
-   <a href="/language/namespaces.html" class="link">namespaces</a>

ReflectionFunctionAbstract::getStartLine
========================================

Gets starting line number

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">ReflectionFunctionAbstract::getStartLine</span> (
<span class="methodparam">void</span> )

Gets the starting line number of the function.

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

The starting line number.

### See Also

-   <span
    class="methodname">ReflectionFunctionAbstract::getEndLine</span>

ReflectionFunctionAbstract::getStaticVariables
==============================================

Gets static variables

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span
class="methodname">ReflectionFunctionAbstract::getStaticVariables</span>
( <span class="methodparam">void</span> )

Get the static variables.

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

An <span class="type">array</span> of static variables.

### See Also

-   <span
    class="methodname">ReflectionFunctionAbstract::getParameters</span>

ReflectionFunctionAbstract::hasReturnType
=========================================

Checks if the function has a specified return type

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span
class="methodname">ReflectionFunctionAbstract::hasReturnType</span> (
<span class="methodparam">void</span> )

Checks whether the reflected function has a return type specified.

### Parameters

This function has no parameters.

### Return Values

Returns **`TRUE`** if the function is a specified return type, otherwise
**`FALSE`**.

### Examples

**Example \#1 <span
class="methodname">ReflectionFunctionAbstract::hasReturnType</span>
example**

``` php
<?php

function to_int($param) : int {
    return (int) $param;
}

$reflection1 = new ReflectionFunction('to_int');
var_dump($reflection1->hasReturnType());
```

The above example will output:

    bool(true)

**Example \#2 Usage on built-in functions**

``` php
<?php

$reflection2 = new ReflectionFunction('array_merge');

var_dump($reflection2->hasReturnType());
```

The above example will output:

    bool(false)

This is because many internal functions do not have types specified for
their parameters or return values. It is therefore best to avoid using
this method on built-in functions.

### See Also

-   <span
    class="methodname">ReflectionFunctionAbstract::getReturnType</span>

ReflectionFunctionAbstract::inNamespace
=======================================

Checks if function in namespace

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ReflectionFunctionAbstract::inNamespace</span>
( <span class="methodparam">void</span> )

Checks whether a function is defined in a namespace.

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

**`TRUE`** if it's in a namespace, otherwise **`FALSE`**

### See Also

-   <span
    class="methodname">ReflectionFunctionAbstract::getNamespaceName</span>
-   <a href="/language/namespaces.html" class="link">namespaces</a>

ReflectionFunctionAbstract::isClosure
=====================================

Checks if closure

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ReflectionFunctionAbstract::isClosure</span> (
<span class="methodparam">void</span> )

Checks whether the reflected function is a <span
class="classname">Closure</span>.

### Parameters

This function has no parameters.

### Return Values

Returns **`TRUE`** if the function is a <span
class="classname">Closure</span>, otherwise **`FALSE`**.

### Examples

**Example \#1 <span
class="methodname">ReflectionFunctionAbstract::isClosure</span>
example**

``` php
<?php
// Non-closure
$function1 = 'str_replace';
$reflection1 = new ReflectionFunction($function1);
var_dump($reflection1->isClosure());

// Closure
$function2 = function () {};
$reflection2 = new ReflectionFunction($function2);
var_dump($reflection2->isClosure());
?>
```

The above example will output:

    bool(false)
    bool(true)

### See Also

-   <span
    class="methodname">ReflectionFunctionAbstract::isGenerator</span>

ReflectionFunctionAbstract::isDeprecated
========================================

Checks if deprecated

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ReflectionFunctionAbstract::isDeprecated</span>
( <span class="methodparam">void</span> )

Checks whether the function is deprecated.

### Parameters

This function has no parameters.

### Return Values

**`TRUE`** if it's deprecated, otherwise **`FALSE`**

### Examples

**Example \#1 <span
class="methodname">ReflectionFunctionAbstract::isDeprecated</span>
example**

``` php
<?php
$rf = new ReflectionFunction('ereg');
var_dump($rf->isDeprecated());
?>
```

The above example will output:

    bool(true)

### See Also

-   <span
    class="methodname">ReflectionFunctionAbstract::getDocComment</span>

ReflectionFunctionAbstract::isGenerator
=======================================

Returns whether this function is a generator

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ReflectionFunctionAbstract::isGenerator</span>
( <span class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

Returns **`TRUE`** if the function is generator, **`FALSE`** if it is
not or **`NULL`** on failure.

ReflectionFunctionAbstract::isInternal
======================================

Checks if is internal

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ReflectionFunctionAbstract::isInternal</span> (
<span class="methodparam">void</span> )

Checks whether the function is internal, as opposed to user-defined.

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

**`TRUE`** if it's internal, otherwise **`FALSE`**

### See Also

-   <span
    class="methodname">ReflectionFunctionAbstract::isUserDefined</span>

ReflectionFunctionAbstract::isUserDefined
=========================================

Checks if user defined

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span
class="methodname">ReflectionFunctionAbstract::isUserDefined</span> (
<span class="methodparam">void</span> )

Checks whether the function is user-defined, as opposed to internal.

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

**`TRUE`** if it's user-defined, otherwise false;

### See Also

-   <span
    class="methodname">ReflectionFunctionAbstract::isInternal</span>

ReflectionFunctionAbstract::isVariadic
======================================

Checks if the function is variadic

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ReflectionFunctionAbstract::isVariadic</span> (
<span class="methodparam">void</span> )

Checks if the function is
<a href="/functions/arguments.html#functions.variable-arg-list" class="link">variadic</a>.

### Parameters

This function has no parameters.

### Return Values

Returns **`TRUE`** if the function is variadic, otherwise **`FALSE`**.

ReflectionFunctionAbstract::returnsReference
============================================

Checks if returns reference

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span
class="methodname">ReflectionFunctionAbstract::returnsReference</span> (
<span class="methodparam">void</span> )

Checks whether the function returns a reference.

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

**`TRUE`** if it returns a reference, otherwise **`FALSE`**

### See Also

-   <span
    class="methodname">ReflectionFunctionAbstract::isClosure</span>

ReflectionFunctionAbstract::\_\_toString
========================================

To string

### Description

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type">void</span> <span
class="methodname">ReflectionFunctionAbstract::\_\_toString</span> (
<span class="methodparam">void</span> )

To string.

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

The string.

### See Also

-   <span class="methodname">ReflectionClass::clone</span>
-   <a href="/language/oop5/magic.html#object.tostring" class="link">__toString()</a>

Introduction
------------

The <span class="classname">ReflectionMethod</span> class reports
information about a method.

Class synopsis
--------------

**ReflectionMethod**

<span class="ooclass"> class **ReflectionMethod** </span> <span
class="ooclass"> <span class="modifier">extends</span>
**ReflectionFunctionAbstract** </span> <span
class="oointerface">implements <span
class="interfacename">Reflector</span> </span> {

/\* Constants \*/

<span class="modifier">const</span> <span class="type">int</span>
`ReflectionMethod::IS_STATIC` <span class="initializer"> = 1</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`ReflectionMethod::IS_PUBLIC` <span class="initializer"> = 256</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`ReflectionMethod::IS_PROTECTED` <span class="initializer"> = 512</span>
;

<span class="modifier">const</span> <span class="type">int</span>
`ReflectionMethod::IS_PRIVATE` <span class="initializer"> = 1024</span>
;

<span class="modifier">const</span> <span class="type">int</span>
`ReflectionMethod::IS_ABSTRACT` <span class="initializer"> = 2</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`ReflectionMethod::IS_FINAL` <span class="initializer"> = 4</span> ;

/\* Properties \*/

<span class="modifier">public</span> `$name` ;

<span class="modifier">public</span> `$class` ;

/\* Methods \*/

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> ( <span
class="methodparam"><span class="type"><span
class="type">string</span><span class="type">object</span></span>
`$class`</span> , <span class="methodparam"><span
class="type">string</span> `$name`</span> )

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">string</span> <span
class="methodname">export</span> ( <span class="methodparam"><span
class="type">string</span> `$class`</span> , <span
class="methodparam"><span class="type">string</span> `$name`</span> \[,
<span class="methodparam"><span class="type">bool</span> `$return`<span
class="initializer"> = **`FALSE`**</span></span> \] )

<span class="modifier">public</span> <span class="type">Closure</span>
<span class="methodname">getClosure</span> ( <span
class="methodparam"><span class="type">object</span> `$object`</span> )

<span class="modifier">public</span> <span
class="type">ReflectionClass</span> <span
class="methodname">getDeclaringClass</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getModifiers</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="type">ReflectionMethod</span> <span
class="methodname">getPrototype</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">invoke</span> ( <span class="methodparam"><span
class="type">object</span> `$object`</span> , <span
class="methodparam"><span class="type">mixed</span> `$args`</span> )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">invokeArgs</span> ( <span
class="methodparam"><span class="type">object</span> `$object`</span> ,
<span class="methodparam"><span class="type">array</span> `$args`</span>
)

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">isAbstract</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">isConstructor</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">isDestructor</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">isFinal</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">isPrivate</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">isProtected</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">isPublic</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">isStatic</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">setAccessible</span> ( <span
class="methodparam"><span class="type">bool</span> `$accessible`</span>
)

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">\_\_toString</span> ( <span
class="methodparam">void</span> )

/\* Inherited methods \*/

<span class="modifier">final</span> <span
class="modifier">private</span> <span class="type">void</span> <span
class="methodname">ReflectionFunctionAbstract::\_\_clone</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="type">ReflectionClass</span> <span
class="methodname">ReflectionFunctionAbstract::getClosureScopeClass</span>
( <span class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">object</span>
<span
class="methodname">ReflectionFunctionAbstract::getClosureThis</span> (
<span class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span
class="methodname">ReflectionFunctionAbstract::getDocComment</span> (
<span class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">ReflectionFunctionAbstract::getEndLine</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="type">ReflectionExtension</span> <span
class="methodname">ReflectionFunctionAbstract::getExtension</span> (
<span class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span
class="methodname">ReflectionFunctionAbstract::getExtensionName</span> (
<span class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">ReflectionFunctionAbstract::getFileName</span>
( <span class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">ReflectionFunctionAbstract::getName</span> (
<span class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span
class="methodname">ReflectionFunctionAbstract::getNamespaceName</span> (
<span class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">ReflectionFunctionAbstract::getNumberOfParameters</span>
( <span class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">ReflectionFunctionAbstract::getNumberOfRequiredParameters</span>
( <span class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span
class="methodname">ReflectionFunctionAbstract::getParameters</span> (
<span class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="type">ReflectionType</span> <span
class="methodname">ReflectionFunctionAbstract::getReturnType</span> (
<span class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">ReflectionFunctionAbstract::getShortName</span>
( <span class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">ReflectionFunctionAbstract::getStartLine</span> (
<span class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span
class="methodname">ReflectionFunctionAbstract::getStaticVariables</span>
( <span class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span
class="methodname">ReflectionFunctionAbstract::hasReturnType</span> (
<span class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ReflectionFunctionAbstract::inNamespace</span>
( <span class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ReflectionFunctionAbstract::isClosure</span> (
<span class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ReflectionFunctionAbstract::isDeprecated</span>
( <span class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ReflectionFunctionAbstract::isGenerator</span>
( <span class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ReflectionFunctionAbstract::isInternal</span> (
<span class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span
class="methodname">ReflectionFunctionAbstract::isUserDefined</span> (
<span class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ReflectionFunctionAbstract::isVariadic</span> (
<span class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span
class="methodname">ReflectionFunctionAbstract::returnsReference</span> (
<span class="methodparam">void</span> )

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type">void</span> <span
class="methodname">ReflectionFunctionAbstract::\_\_toString</span> (
<span class="methodparam">void</span> )

}

Properties
----------

`name`  
Method name

`class`  
Class name

Predefined Constants
--------------------

ReflectionMethod Modifiers
--------------------------

**`ReflectionMethod::IS_STATIC`**  
Indicates that the method is static.

**`ReflectionMethod::IS_PUBLIC`**  
Indicates that the method is public.

**`ReflectionMethod::IS_PROTECTED`**  
Indicates that the method is protected.

**`ReflectionMethod::IS_PRIVATE`**  
Indicates that the method is private.

**`ReflectionMethod::IS_ABSTRACT`**  
Indicates that the method is abstract.

**`ReflectionMethod::IS_FINAL`**  
Indicates that the method is final.

ReflectionMethod::\_\_construct
===============================

Constructs a ReflectionMethod

### Description

<span class="modifier">public</span> <span
class="methodname">ReflectionMethod::\_\_construct</span> ( <span
class="methodparam"><span class="type"><span
class="type">string</span><span class="type">object</span></span>
`$class`</span> , <span class="methodparam"><span
class="type">string</span> `$name`</span> )

<span class="modifier">public</span> <span
class="methodname">ReflectionMethod::\_\_construct</span> ( <span
class="methodparam"><span class="type">string</span>
`$class_method`</span> )

Constructs a new <span class="classname">ReflectionMethod</span>.

### Parameters

`class`  
Classname or object (instance of the class) that contains the method.

`name`  
Name of the method.

`class_method`  
Class name and method name delimited by *::*.

### Return Values

No value is returned.

### Errors/Exceptions

A <span class="classname">ReflectionException</span> is thrown if the
given method does not exist.

### Examples

**Example \#1 <span
class="methodname">ReflectionMethod::\_\_construct</span> example**

``` php
<?php
class Counter
{
    private static $c = 0;

    /**
     * Increment counter
     *
     * @final
     * @static
     * @access  public
     * @return  int
     */
    final public static function increment()
    {
        return ++self::$c;
    }
}

// Create an instance of the ReflectionMethod class
$method = new ReflectionMethod('Counter', 'increment');

// Print out basic information
printf(
    "===> The %s%s%s%s%s%s%s method '%s' (which is %s)\n" .
    "     declared in %s\n" .
    "     lines %d to %d\n" .
    "     having the modifiers %d[%s]\n",
        $method->isInternal() ? 'internal' : 'user-defined',
        $method->isAbstract() ? ' abstract' : '',
        $method->isFinal() ? ' final' : '',
        $method->isPublic() ? ' public' : '',
        $method->isPrivate() ? ' private' : '',
        $method->isProtected() ? ' protected' : '',
        $method->isStatic() ? ' static' : '',
        $method->getName(),
        $method->isConstructor() ? 'the constructor' : 'a regular method',
        $method->getFileName(),
        $method->getStartLine(),
        $method->getEndline(),
        $method->getModifiers(),
        implode(' ', Reflection::getModifierNames($method->getModifiers()))
);

// Print documentation comment
printf("---> Documentation:\n %s\n", var_export($method->getDocComment(), true));

// Print static variables if existant
if ($statics= $method->getStaticVariables()) {
    printf("---> Static variables: %s\n", var_export($statics, true));
}

// Invoke the method
printf("---> Invocation results in: ");
var_dump($method->invoke(NULL));
?>
```

The above example will output something similar to:

    ===> The user-defined final public static method 'increment' (which is a regular method)
         declared in /Users/philip/cvs/phpdoc/test.php
         lines 14 to 17
         having the modifiers 261[final public static]
    ---> Documentation:
     '/**
         * Increment counter
         *
         * @final
         * @static
         * @access  public
         * @return  int
         */'
    ---> Invocation results in: int(1)

### See Also

-   <span class="methodname">ReflectionMethod::export</span>
-   <a href="/language/oop5/decon.html#language.oop5.decon.constructor" class="link">Constructors</a>

ReflectionMethod::export
========================

Export a reflection method

**Warning**

This function has been *DEPRECATED* as of PHP 7.4.0. Relying on this
function is highly discouraged.

### Description

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">string</span> <span
class="methodname">ReflectionMethod::export</span> ( <span
class="methodparam"><span class="type">string</span> `$class`</span> ,
<span class="methodparam"><span class="type">string</span>
`$name`</span> \[, <span class="methodparam"><span
class="type">bool</span> `$return`<span class="initializer"> =
**`FALSE`**</span></span> \] )

Exports a ReflectionMethod.

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`class`  
The class name.

`name`  
The name of the method.

`return`  
Setting to **`TRUE`** will return the export, as opposed to emitting it.
Setting to **`FALSE`** (the default) will do the opposite.

### Return Values

If the `return` parameter is set to **`TRUE`**, then the export is
returned as a <span class="type">string</span>, otherwise **`NULL`** is
returned.

### See Also

-   <span class="methodname">ReflectionMethod::\_\_construct</span>
-   <span class="methodname">ReflectionMethod::\_\_toString</span>

ReflectionMethod::getClosure
============================

Returns a dynamically created closure for the method

### Description

<span class="modifier">public</span> <span class="type">Closure</span>
<span class="methodname">ReflectionMethod::getClosure</span> ( <span
class="methodparam"><span class="type">object</span> `$object`</span> )

<span class="modifier">public</span> <span class="type">Closure</span>
<span class="methodname">ReflectionMethod::getClosure</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`object`  
Forbidden for static methods, required for other methods.

### Return Values

Returns <span class="classname">Closure</span>. Returns **`NULL`** in
case of an error.

ReflectionMethod::getDeclaringClass
===================================

Gets declaring class for the reflected method

### Description

<span class="modifier">public</span> <span
class="type">ReflectionClass</span> <span
class="methodname">ReflectionMethod::getDeclaringClass</span> ( <span
class="methodparam">void</span> )

Gets the declaring class for the reflected method.

### Parameters

This function has no parameters.

### Return Values

A <span class="classname">ReflectionClass</span> object of the class
that the reflected method is part of.

### Examples

**Example \#1 <span
class="methodname">ReflectionMethod::getDeclaringClass</span> example**

``` php
<?php
class HelloWorld {

    protected function sayHelloTo($name) {
        return 'Hello ' . $name;
    }

}

$reflectionMethod = new ReflectionMethod(new HelloWorld(), 'sayHelloTo');
var_dump($reflectionMethod->getDeclaringClass());
?>
```

The above example will output:

    object(ReflectionClass)#2 (1) {
      ["name"]=>
      string(10) "HelloWorld"
    }

### See Also

-   <span class="methodname">ReflectionMethod::isAbstract</span>

ReflectionMethod::getModifiers
==============================

Gets the method modifiers

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">ReflectionMethod::getModifiers</span> ( <span
class="methodparam">void</span> )

Returns a bitfield of the access modifiers for this method.

### Parameters

This function has no parameters.

### Return Values

A numeric representation of the modifiers. The modifiers are listed
below. The actual meanings of these modifiers are described in the
<a href="/class/reflectionmethod.html#ReflectionMethod%20Modifiers" class="link">predefined constants</a>.

### Examples

**Example \#1 <span
class="methodname">ReflectionMethod::getModifiers</span> example**

``` php
<?php
class Testing
{
    final public static function foo()
    {
        return;
    }
    public function bar()
    {
        return;
    }
}

$foo = new ReflectionMethod('Testing', 'foo');

echo "Modifiers for method foo():\n";
echo $foo->getModifiers() . "\n";
echo implode(' ', Reflection::getModifierNames($foo->getModifiers())) . "\n";

$bar = new ReflectionMethod('Testing', 'bar');

echo "Modifiers for method bar():\n";
echo $bar->getModifiers() . "\n";
echo implode(' ', Reflection::getModifierNames($bar->getModifiers()));
?>
```

The above example will output something similar to:

    Modifiers for method foo():
    261
    final public static
    Modifiers for method bar():
    65792
    public

### See Also

-   <span class="methodname">Reflection::getModifierNames</span>

ReflectionMethod::getPrototype
==============================

Gets the method prototype (if there is one)

### Description

<span class="modifier">public</span> <span
class="type">ReflectionMethod</span> <span
class="methodname">ReflectionMethod::getPrototype</span> ( <span
class="methodparam">void</span> )

Returns the methods prototype.

### Parameters

This function has no parameters.

### Return Values

A <span class="classname">ReflectionMethod</span> instance of the method
prototype.

### Errors/Exceptions

A <span class="classname">ReflectionException</span> exception is thrown
if the method does not have a prototype.

### Examples

**Example \#1 <span
class="methodname">ReflectionMethod::getPrototype</span> example**

``` php
<?php
class Hello {

    public function sayHelloTo($name) {
        return 'Hello ' . $name;
    }

}
class HelloWorld extends Hello {

    public function sayHelloTo($name) {
        return 'Hello world: ' . $name;
    }

}

$reflectionMethod = new ReflectionMethod('HelloWorld', 'sayHelloTo');
var_dump($reflectionMethod->getPrototype());
?>
```

The above example will output:

    object(ReflectionMethod)#2 (2) {
      ["name"]=>
      string(10) "sayHelloTo"
      ["class"]=>
      string(5) "Hello"
    }

### See Also

-   <span class="methodname">ReflectionMethod::getModifiers</span>

ReflectionMethod::invoke
========================

Invoke

### Description

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">ReflectionMethod::invoke</span> ( <span
class="methodparam"><span class="type">object</span> `$object`</span> ,
<span class="methodparam"><span class="type">mixed</span> `$args`</span>
)

Invokes a reflected method.

### Parameters

`object`  
The object to invoke the method on. For static methods, pass <span
class="type">null</span> to this parameter.

`args`  
Zero or more parameters to be passed to the method. It accepts a
variable number of parameters which are passed to the method.

### Return Values

Returns the method result.

### Errors/Exceptions

A <span class="classname">ReflectionException</span> if the `object`
parameter does not contain an instance of the class that this method was
declared in.

A <span class="classname">ReflectionException</span> if the method
invocation failed.

### Examples

**Example \#1 <span class="methodname">ReflectionMethod::invoke</span>
example**

``` php
<?php
class HelloWorld {

    public function sayHelloTo($name) {
        return 'Hello ' . $name;
    }

}

$reflectionMethod = new ReflectionMethod('HelloWorld', 'sayHelloTo');
echo $reflectionMethod->invoke(new HelloWorld(), 'Mike');
?>
```

The above example will output:

    Hello Mike

### Notes

> **Note**:
>
> If the function has arguments that need to be references, then they
> must be references in the passed argument list.

### See Also

-   <span class="methodname">ReflectionMethod::invokeArgs</span>
-   <a href="/language/oop5/magic.html#object.invoke" class="link">__invoke()</a>
-   <span class="function">call\_user\_func</span>

ReflectionMethod::invokeArgs
============================

Invoke args

### Description

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">ReflectionMethod::invokeArgs</span> ( <span
class="methodparam"><span class="type">object</span> `$object`</span> ,
<span class="methodparam"><span class="type">array</span> `$args`</span>
)

Invokes the reflected method and pass its arguments as array.

### Parameters

`object`  
The object to invoke the method on. In case of static methods, you can
pass <span class="type">null</span> to this parameter.

`args`  
The parameters to be passed to the function, as an <span
class="type">array</span>.

### Return Values

Returns the method result.

### Errors/Exceptions

A <span class="classname">ReflectionException</span> if the `object`
parameter does not contain an instance of the class that this method was
declared in.

A <span class="classname">ReflectionException</span> if the method
invocation failed.

### Examples

**Example \#1 <span
class="methodname">ReflectionMethod::invokeArgs</span> example**

``` php
<?php
class HelloWorld {

    public function sayHelloTo($name) {
        return 'Hello ' . $name;
    }

}

$reflectionMethod = new ReflectionMethod('HelloWorld', 'sayHelloTo');
echo $reflectionMethod->invokeArgs(new HelloWorld(), array('Mike'));
?>
```

The above example will output:

    Hello Mike

### Notes

> **Note**:
>
> If the function has arguments that need to be references, then they
> must be references in the passed argument list.

### See Also

-   <span class="methodname">ReflectionMethod::invoke</span>
-   <a href="/language/oop5/magic.html#object.invoke" class="link">__invoke()</a>
-   <span class="function">call\_user\_func\_array</span>

ReflectionMethod::isAbstract
============================

Checks if method is abstract

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ReflectionMethod::isAbstract</span> ( <span
class="methodparam">void</span> )

Checks if the method is abstract.

### Parameters

This function has no parameters.

### Return Values

**`TRUE`** if the method is abstract, otherwise **`FALSE`**

### See Also

-   <span class="methodname">ReflectionMethod::getDeclaringClass</span>

ReflectionMethod::isConstructor
===============================

Checks if method is a constructor

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ReflectionMethod::isConstructor</span> ( <span
class="methodparam">void</span> )

Checks if the method is a constructor.

### Parameters

This function has no parameters.

### Return Values

**`TRUE`** if the method is a constructor, otherwise **`FALSE`**

### See Also

-   <span class="methodname">ReflectionMethod::\_\_construct</span>
-   <span class="methodname">ReflectionMethod::isAbstract</span>
-   <span class="methodname">ReflectionMethod::isDestructor</span>

ReflectionMethod::isDestructor
==============================

Checks if method is a destructor

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ReflectionMethod::isDestructor</span> ( <span
class="methodparam">void</span> )

Checks if the method is a destructor.

### Parameters

This function has no parameters.

### Return Values

**`TRUE`** if the method is a destructor, otherwise **`FALSE`**

### See Also

-   <span class="methodname">ReflectionMethod::isConstructor</span>

ReflectionMethod::isFinal
=========================

Checks if method is final

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ReflectionMethod::isFinal</span> ( <span
class="methodparam">void</span> )

Checks if the method is final.

### Parameters

This function has no parameters.

### Return Values

**`TRUE`** if the method is final, otherwise **`FALSE`**

### See Also

-   <span class="methodname">ReflectionMethod::isStatic</span>

ReflectionMethod::isPrivate
===========================

Checks if method is private

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ReflectionMethod::isPrivate</span> ( <span
class="methodparam">void</span> )

Checks if the method is private.

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

**`TRUE`** if the method is private, otherwise **`FALSE`**

### See Also

-   <span class="methodname">ReflectionMethod::isPublic</span>

ReflectionMethod::isProtected
=============================

Checks if method is protected

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ReflectionMethod::isProtected</span> ( <span
class="methodparam">void</span> )

Checks if the method is protected.

### Parameters

This function has no parameters.

### Return Values

**`TRUE`** if the method is protected, otherwise **`FALSE`**

### See Also

-   <span class="methodname">ReflectionMethod::isPrivate</span>

ReflectionMethod::isPublic
==========================

Checks if method is public

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ReflectionMethod::isPublic</span> ( <span
class="methodparam">void</span> )

Checks if the method is public.

### Parameters

This function has no parameters.

### Return Values

**`TRUE`** if the method is public, otherwise **`FALSE`**

### See Also

-   <span class="methodname">ReflectionMethod::isPrivate</span>

ReflectionMethod::isStatic
==========================

Checks if method is static

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ReflectionMethod::isStatic</span> ( <span
class="methodparam">void</span> )

Checks if the method is static.

### Parameters

This function has no parameters.

### Return Values

**`TRUE`** if the method is static, otherwise **`FALSE`**

### See Also

-   <span class="methodname">ReflectionMethod::isFinal</span>

ReflectionMethod::setAccessible
===============================

Set method accessibility

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">ReflectionMethod::setAccessible</span> ( <span
class="methodparam"><span class="type">bool</span> `$accessible`</span>
)

Sets a method to be accessible. For example, it may allow protected and
private methods to be invoked.

### Parameters

`accessible`  
**`TRUE`** to allow accessibility, or **`FALSE`**.

### Return Values

No value is returned.

### See Also

-   <span class="methodname">ReflectionMethod::isPrivate</span>
-   <span class="methodname">ReflectionMethod::isProtected</span>

ReflectionMethod::\_\_toString
==============================

Returns the string representation of the Reflection method object

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">ReflectionMethod::\_\_toString</span> ( <span
class="methodparam">void</span> )

Returns the string representation of the Reflection method object.

### Parameters

This function has no parameters.

### Return Values

A string representation of this <span
class="classname">ReflectionMethod</span> instance.

### Examples

**Example \#1 <span
class="methodname">ReflectionMethod::\_\_toString</span> example**

``` php
<?php
class HelloWorld {

    public function sayHelloTo($name) {
        return 'Hello ' . $name;
    }

}

$reflectionMethod = new ReflectionMethod(new HelloWorld(), 'sayHelloTo');
echo $reflectionMethod;
?>
```

The above example will output:

    Method [ <user> public method sayHelloTo ] {
      @@ /var/www/examples/reflection.php 16 - 18

      - Parameters [1] {
        Parameter #0 [ <required> $name ]
      }
    }

### See Also

-   <span class="methodname">ReflectionMethod::export</span>
-   <a href="/language/oop5/magic.html#object.tostring" class="link">__toString()</a>

Introduction
------------

Class synopsis
--------------

**ReflectionNamedType**

<span class="ooclass"> class **ReflectionNamedType** </span> <span
class="ooclass"> <span class="modifier">extends</span>
**ReflectionType** </span> {

/\* Methods \*/

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getName</span> ( <span
class="methodparam">void</span> )

/\* Inherited methods \*/

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ReflectionType::allowsNull</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ReflectionType::isBuiltin</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">ReflectionType::\_\_toString</span> ( <span
class="methodparam">void</span> )

}

ReflectionNamedType::getName
============================

Get the text of the type hint

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">ReflectionNamedType::getName</span> ( <span
class="methodparam">void</span> )

### Parameters

This function has no parameters.

### Return Values

Returns the text of the type hint.

### See Also

-   <span class="methodname">ReflectionType::\_\_toString</span>

Introduction
------------

The <span class="classname">ReflectionObject</span> class reports
information about an <span class="type">object</span>.

Class synopsis
--------------

**ReflectionObject**

<span class="ooclass"> class **ReflectionObject** </span> <span
class="ooclass"> <span class="modifier">extends</span>
**ReflectionClass** </span> <span class="oointerface">implements <span
class="interfacename">Reflector</span> </span> {

/\* Inherited constants \*/

<span class="modifier">const</span> <span class="type">int</span>
`ReflectionClass::IS_IMPLICIT_ABSTRACT` <span class="initializer"> =
16</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`ReflectionClass::IS_EXPLICIT_ABSTRACT` <span class="initializer"> =
32</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`ReflectionClass::IS_FINAL` <span class="initializer"> = 64</span> ;

/\* Properties \*/

<span class="modifier">public</span> `$name` ;

/\* Methods \*/

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> ( <span
class="methodparam"><span class="type">object</span> `$argument`</span>
)

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">string</span> <span
class="methodname">export</span> ( <span class="methodparam"><span
class="type">string</span> `$argument`</span> \[, <span
class="methodparam"><span class="type">bool</span> `$return`</span> \] )

/\* Inherited methods \*/

<span class="modifier">public</span> <span
class="methodname">ReflectionClass::\_\_construct</span> ( <span
class="methodparam"><span class="type">mixed</span> `$argument`</span> )

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">string</span> <span
class="methodname">ReflectionClass::export</span> ( <span
class="methodparam"><span class="type">mixed</span> `$argument`</span>
\[, <span class="methodparam"><span class="type">bool</span>
`$return`<span class="initializer"> = **`FALSE`**</span></span> \] )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">ReflectionClass::getConstant</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">ReflectionClass::getConstants</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="type">ReflectionMethod</span> <span
class="methodname">ReflectionClass::getConstructor</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">ReflectionClass::getDefaultProperties</span> (
<span class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">ReflectionClass::getDocComment</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">ReflectionClass::getEndLine</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="type">ReflectionExtension</span> <span
class="methodname">ReflectionClass::getExtension</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">ReflectionClass::getExtensionName</span> (
<span class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">ReflectionClass::getFileName</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">ReflectionClass::getInterfaceNames</span> (
<span class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">ReflectionClass::getInterfaces</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="type">ReflectionMethod</span> <span
class="methodname">ReflectionClass::getMethod</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">ReflectionClass::getMethods</span> (\[ <span
class="methodparam"><span class="type">int</span> `$filter`</span> \] )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">ReflectionClass::getModifiers</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">ReflectionClass::getName</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">ReflectionClass::getNamespaceName</span> (
<span class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="type">ReflectionClass</span> <span
class="methodname">ReflectionClass::getParentClass</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">ReflectionClass::getProperties</span> (\[ <span
class="methodparam"><span class="type">int</span> `$filter`</span> \] )

<span class="modifier">public</span> <span
class="type">ReflectionProperty</span> <span
class="methodname">ReflectionClass::getProperty</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> )

<span class="modifier">public</span> <span
class="type">ReflectionClassConstant</span> <span
class="methodname">ReflectionClass::getReflectionConstant</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">ReflectionClass::getReflectionConstants</span>
( <span class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">ReflectionClass::getShortName</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">ReflectionClass::getStartLine</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">ReflectionClass::getStaticProperties</span> (
<span class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">ReflectionClass::getStaticPropertyValue</span>
( <span class="methodparam"><span class="type">string</span>
`$name`</span> \[, <span class="methodparam"><span
class="type">mixed</span> `&$def_value`</span> \] )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">ReflectionClass::getTraitAliases</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">ReflectionClass::getTraitNames</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">ReflectionClass::getTraits</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ReflectionClass::hasConstant</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ReflectionClass::hasMethod</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ReflectionClass::hasProperty</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ReflectionClass::implementsInterface</span> (
<span class="methodparam"><span class="type">string</span>
`$interface`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ReflectionClass::inNamespace</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ReflectionClass::isAbstract</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ReflectionClass::isAnonymous</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ReflectionClass::isCloneable</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ReflectionClass::isFinal</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ReflectionClass::isInstance</span> ( <span
class="methodparam"><span class="type">object</span> `$object`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ReflectionClass::isInstantiable</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ReflectionClass::isInterface</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ReflectionClass::isInternal</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ReflectionClass::isIterable</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ReflectionClass::isSubclassOf</span> ( <span
class="methodparam"><span class="type">mixed</span> `$class`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ReflectionClass::isTrait</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ReflectionClass::isUserDefined</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">object</span>
<span class="methodname">ReflectionClass::newInstance</span> ( <span
class="methodparam"><span class="type">mixed</span> `$args`</span> )

<span class="modifier">public</span> <span class="type">object</span>
<span class="methodname">ReflectionClass::newInstanceArgs</span> (\[
<span class="methodparam"><span class="type">array</span> `$args`</span>
\] )

<span class="modifier">public</span> <span class="type">object</span>
<span
class="methodname">ReflectionClass::newInstanceWithoutConstructor</span>
( <span class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">ReflectionClass::setStaticPropertyValue</span>
( <span class="methodparam"><span class="type">string</span>
`$name`</span> , <span class="methodparam"><span
class="type">mixed</span> `$value`</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">ReflectionClass::\_\_toString</span> ( <span
class="methodparam">void</span> )

}

Properties
----------

`name`  
Name of the object's class. Read-only, throws <span
class="classname">ReflectionException</span> in attempt to write.

ReflectionObject::\_\_construct
===============================

Constructs a ReflectionObject

### Description

<span class="modifier">public</span> <span
class="methodname">ReflectionObject::\_\_construct</span> ( <span
class="methodparam"><span class="type">object</span> `$argument`</span>
)

Constructs a <span class="classname">ReflectionObject</span>.

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`argument`  
An object instance.

### Return Values

No value is returned.

### See Also

-   <span class="methodname">ReflectionObject::export</span>
-   <a href="/language/oop5/decon.html#language.oop5.decon.constructor" class="link">Constructors</a>

ReflectionObject::export
========================

Export

### Description

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">string</span> <span
class="methodname">ReflectionObject::export</span> ( <span
class="methodparam"><span class="type">string</span> `$argument`</span>
\[, <span class="methodparam"><span class="type">bool</span>
`$return`</span> \] )

Exports a reflection.

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`argument`  
The reflection to export.

`return`  
Setting to **`TRUE`** will return the export, as opposed to emitting it.
Setting to **`FALSE`** (the default) will do the opposite.

### Return Values

If the `return` parameter is set to **`TRUE`**, then the export is
returned as a <span class="type">string</span>, otherwise **`NULL`** is
returned.

### See Also

-   <span class="methodname">ReflectionObject::\_\_construct</span>

Introduction
------------

The <span class="classname">ReflectionParameter</span> class retrieves
information about function's or method's parameters.

To introspect function parameters, first create an instance of the <span
class="classname">ReflectionFunction</span> or <span
class="classname">ReflectionMethod</span> classes and then use their
<span
class="methodname">ReflectionFunctionAbstract::getParameters</span>
method to retrieve an array of parameters.

Class synopsis
--------------

**ReflectionParameter**

<span class="ooclass"> class **ReflectionParameter** </span> <span
class="oointerface">implements <span
class="interfacename">Reflector</span> </span> {

/\* Properties \*/

<span class="modifier">public</span> `$name` ;

/\* Methods \*/

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">allowsNull</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">canBePassedByValue</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span
class="modifier">private</span> <span class="type">void</span> <span
class="methodname">\_\_clone</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> ( <span
class="methodparam"><span class="type">callable</span>
`$function`</span> , <span class="methodparam"><span
class="type">mixed</span> `$parameter`</span> )

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">string</span> <span
class="methodname">export</span> ( <span class="methodparam"><span
class="type">string</span> `$function`</span> , <span
class="methodparam"><span class="type">string</span> `$parameter`</span>
\[, <span class="methodparam"><span class="type">bool</span>
`$return`</span> \] )

<span class="modifier">public</span> <span
class="type">ReflectionClass</span> <span
class="methodname">getClass</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="type">ReflectionClass</span> <span
class="methodname">getDeclaringClass</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="type">ReflectionFunctionAbstract</span> <span
class="methodname">getDeclaringFunction</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">getDefaultValue</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getDefaultValueConstantName</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getName</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getPosition</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="type">ReflectionType</span> <span
class="methodname">getType</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">hasType</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">isArray</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">isCallable</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">isDefaultValueAvailable</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">isDefaultValueConstant</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">isOptional</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">isPassedByReference</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">isVariadic</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">\_\_toString</span> ( <span
class="methodparam">void</span> )

}

Properties
----------

`name`  
Name of the parameter. Read-only, throws <span
class="classname">ReflectionException</span> in attempt to write.

ReflectionParameter::allowsNull
===============================

Checks if null is allowed

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ReflectionParameter::allowsNull</span> ( <span
class="methodparam">void</span> )

Checks whether the parameter allows **`NULL`**.

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

**`TRUE`** if **`NULL`** is allowed, otherwise **`FALSE`**

### See Also

-   <span class="methodname">ReflectionParameter::isOptional</span>

ReflectionParameter::canBePassedByValue
=======================================

Returns whether this parameter can be passed by value

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ReflectionParameter::canBePassedByValue</span>
( <span class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

Returns **`TRUE`** if the parameter can be passed by value, **`FALSE`**
otherwise. Returns **`NULL`** in case of an error.

ReflectionParameter::\_\_clone
==============================

Clone

### Description

<span class="modifier">final</span> <span
class="modifier">private</span> <span class="type">void</span> <span
class="methodname">ReflectionParameter::\_\_clone</span> ( <span
class="methodparam">void</span> )

Clones.

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

### See Also

-   <span class="methodname">ReflectionParameter::toString</span>
-   <a href="/language/oop5/cloning.html" class="link">Object cloning</a>

ReflectionParameter::\_\_construct
==================================

Construct

### Description

<span class="modifier">public</span> <span
class="methodname">ReflectionParameter::\_\_construct</span> ( <span
class="methodparam"><span class="type">callable</span>
`$function`</span> , <span class="methodparam"><span
class="type">mixed</span> `$parameter`</span> )

Constructs a <span class="classname">ReflectionParameter</span>
instance.

### Parameters

`function`  
The function to reflect parameters from.

`parameter`  
Either an <span class="type">int</span> specifying the position of the
parameter (starting with zero), or a the parameter name as <span
class="type">string</span>.

### Return Values

No value is returned.

### Examples

**Example \#1 Using the <span
class="classname">ReflectionParameter</span> class**

``` php
<?php
function foo($a, $b, $c) { }
function bar(Exception $a, &$b, $c) { }
function baz(ReflectionFunction $a, $b = 1, $c = null) { }
function abc() { }

$reflect = new ReflectionFunction('foo');

echo $reflect;

foreach ($reflect->getParameters() as $i => $param) {
    printf(
        "-- Parameter #%d: %s {\n".
        "   Class: %s\n".
        "   Allows NULL: %s\n".
        "   Passed to by reference: %s\n".
        "   Is optional?: %s\n".
        "}\n",
        $i, // $param->getPosition() can be used from PHP 5.2.3
        $param->getName(),
        var_export($param->getClass(), 1),
        var_export($param->allowsNull(), 1),
        var_export($param->isPassedByReference(), 1),
        $param->isOptional() ? 'yes' : 'no'
    );
}
?>
```

The above example will output something similar to:

    Function [ <user> function foo ] {
      @@ /Users/philip/cvs/phpdoc/a 2 - 2

      - Parameters [3] {
        Parameter #0 [ <required> $a ]
        Parameter #1 [ <required> $b ]
        Parameter #2 [ <required> $c ]
      }
    }
    -- Parameter #0: a {
       Class: NULL
       Allows NULL: true
       Passed to by reference: false
       Is optional?: no
    }
    -- Parameter #1: b {
       Class: NULL
       Allows NULL: true
       Passed to by reference: false
       Is optional?: no
    }
    -- Parameter #2: c {
       Class: NULL
       Allows NULL: true
       Passed to by reference: false
       Is optional?: no
    }

### See Also

-   <span
    class="methodname">ReflectionFunctionAbstract::getParameters</span>
-   <span class="methodname">ReflectionFunction::\_\_construct</span>
-   <span class="methodname">ReflectionMethod::\_\_construct</span>
-   <a href="/language/oop5/decon.html#language.oop5.decon.constructor" class="link">Constructors</a>

ReflectionParameter::export
===========================

Exports

**Warning**

This function has been *DEPRECATED* as of PHP 7.4.0. Relying on this
function is highly discouraged.

### Description

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">string</span> <span
class="methodname">ReflectionParameter::export</span> ( <span
class="methodparam"><span class="type">string</span> `$function`</span>
, <span class="methodparam"><span class="type">string</span>
`$parameter`</span> \[, <span class="methodparam"><span
class="type">bool</span> `$return`</span> \] )

Exports.

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`function`  
The function name.

`parameter`  
The parameter name.

`return`  
Setting to **`TRUE`** will return the export, as opposed to emitting it.
Setting to **`FALSE`** (the default) will do the opposite.

### Return Values

The exported reflection.

### See Also

-   <span class="methodname">ReflectionParameter::\_\_toString</span>

ReflectionParameter::getClass
=============================

Get the type hinted class

### Description

<span class="modifier">public</span> <span
class="type">ReflectionClass</span> <span
class="methodname">ReflectionParameter::getClass</span> ( <span
class="methodparam">void</span> )

Gets the class type hinted for the parameter as a <span
class="classname">ReflectionClass</span> object.

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

A <span class="classname">ReflectionClass</span> object.

### Examples

**Example \#1 Using the <span
class="classname">ReflectionParameter</span> class**

``` php
<?php
function foo(Exception $a) { }

$functionReflection = new ReflectionFunction('foo');
$parameters = $functionReflection->getParameters();
$aParameter = $parameters[0];

echo $aParameter->getClass()->name;
?>
```

The above example will output:

    Exception

### See Also

-   <span
    class="methodname">ReflectionParameter::getDeclaringClass</span>

ReflectionParameter::getDeclaringClass
======================================

Gets declaring class

### Description

<span class="modifier">public</span> <span
class="type">ReflectionClass</span> <span
class="methodname">ReflectionParameter::getDeclaringClass</span> ( <span
class="methodparam">void</span> )

Gets the declaring class.

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

A <span class="classname">ReflectionClass</span> object or **`NULL`** if
called on function.

### Examples

**Example \#1 Getting the class that declared the method**

``` php
<?php
class Foo
{
    public function bar(\DateTime $datetime)
    {
    }
}

class Baz extends Foo
{
}

$param = new \ReflectionParameter(['Baz', 'bar'], 0); 

var_dump($param->getDeclaringClass());
```

The above example will output:

    object(ReflectionClass)#2 (1) {
      ["name"]=>
      string(3) "Foo"
    }

### See Also

-   <span class="methodname">ReflectionParameter::getClass</span>

ReflectionParameter::getDeclaringFunction
=========================================

Gets declaring function

### Description

<span class="modifier">public</span> <span
class="type">ReflectionFunctionAbstract</span> <span
class="methodname">ReflectionParameter::getDeclaringFunction</span> (
<span class="methodparam">void</span> )

Gets the declaring function.

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

A <span class="classname">ReflectionFunction</span> object.

### See Also

-   <span
    class="methodname">ReflectionParameter::getDeclaringClass</span>

ReflectionParameter::getDefaultValue
====================================

Gets default parameter value

### Description

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">ReflectionParameter::getDefaultValue</span> (
<span class="methodparam">void</span> )

Gets the default value of the parameter for any user-defined or internal
function or method. If the parameter is not optional a <span
class="classname">ReflectionException</span> will be thrown.

### Parameters

This function has no parameters.

### Return Values

The parameters default value.

### Changelog

| Version | Description                                                                                                                                                                                   |
|---------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 8.0.0   | This method now allows getting the default value of parameters of built-in functions and built-in class methods. Previously, a <span class="classname">ReflectionException</span> was thrown. |

### Examples

**Example \#1 Getting default values of function parameters**

``` php
<?php
function foo($test, $bar = 'baz')
{
    echo $test . $bar;
}

$function = new ReflectionFunction('foo');

foreach ($function->getParameters() as $param) {
    echo 'Name: ' . $param->getName() . PHP_EOL;
    if ($param->isOptional()) {
        echo 'Default value: ' . $param->getDefaultValue() . PHP_EOL;
    }
    echo PHP_EOL;
}
?>
```

The above example will output:

    Name: test

    Name: bar
    Default value: baz

### See Also

-   <span class="methodname">ReflectionParameter::isOptional</span>
-   <span
    class="methodname">ReflectionParameter::isDefaultValueAvailable</span>
-   <span
    class="methodname">ReflectionParameter::getDefaultValueConstantName</span>
-   <span
    class="methodname">ReflectionParameter::isPassedByReference</span>

ReflectionParameter::getDefaultValueConstantName
================================================

Returns the default value's constant name if default value is constant
or null

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span
class="methodname">ReflectionParameter::getDefaultValueConstantName</span>
( <span class="methodparam">void</span> )

Returns the default value's constant name of the parameter of any
user-defined or internal function or method, if default value is
constant or null. If the parameter is not optional a <span
class="classname">ReflectionException</span> will be thrown.

### Parameters

This function has no parameters.

### Return Values

Returns string on success or **`NULL`** on failure.

### Changelog

| Version | Description                                                                                                                                                                                      |
|---------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 8.0.0   | This method now allows getting the default values' constant names of built-in functions and built-in class methods. Previously, a <span class="classname">ReflectionException</span> was thrown. |

### Examples

**Example \#1 Getting default values' constant names of function
parameters**

``` php
<?php
function foo($test, $bar = PHP_INT_MIN)
{
    echo $test . $bar;
}

$function = new ReflectionFunction('foo');

foreach ($function->getParameters() as $param) {
    echo 'Name: ' . $param->getName() . PHP_EOL;
    if ($param->isOptional()) {
        echo 'Default value: ' . $param->getDefaultValueConstantName() . PHP_EOL;
    }
    echo PHP_EOL;
}
?>
```

The above example will output:

    Name: test

    Name: bar
    Default value: PHP_INT_MIN

### See Also

-   <span class="methodname">ReflectionParameter::isOptional</span>
-   <span
    class="methodname">ReflectionParameter::isDefaultValueConstant</span>
-   <span class="methodname">ReflectionParameter::getDefaultValue</span>

ReflectionParameter::getName
============================

Gets parameter name

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">ReflectionParameter::getName</span> ( <span
class="methodparam">void</span> )

Gets the name of the parameter.

### Parameters

This function has no parameters.

### Return Values

The name of the reflected parameter.

### See Also

-   <span class="methodname">ReflectionParameter::getValue</span>

ReflectionParameter::getPosition
================================

Gets parameter position

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">ReflectionParameter::getPosition</span> ( <span
class="methodparam">void</span> )

Gets the position of the parameter.

### Parameters

This function has no parameters.

### Return Values

The position of the parameter, left to right, starting at position \#0.

### See Also

-   <span class="methodname">ReflectionParameter::getName</span>

ReflectionParameter::getType
============================

Gets a parameter's type

### Description

<span class="modifier">public</span> <span
class="type">ReflectionType</span> <span
class="methodname">ReflectionParameter::getType</span> ( <span
class="methodparam">void</span> )

Gets the associated type of a parameter.

### Parameters

This function has no parameters.

### Return Values

Returns a <span class="classname">ReflectionType</span> object if a
parameter type is specified, **`NULL`** otherwise.

### Examples

**Example \#1 <span
class="methodname">ReflectionParameter::getType</span> Usage as of PHP
7.1.0**

As of PHP 7.1.0, <span
class="methodname">ReflectionType::\_\_toString</span> is deprecated,
and <span class="methodname">ReflectionParameter::getType</span> *may*
return an instance of <span
class="classname">ReflectionNamedType</span>. To get the name of the
parameter type, <span class="methodname">ReflectionNamedType</span> is
available in this case.

``` php
<?php
function someFunction(int $param, $param2) {}

$reflectionFunc = new ReflectionFunction('someFunction');
$reflectionParams = $reflectionFunc->getParameters();
$reflectionType1 = $reflectionParams[0]->getType();
$reflectionType2 = $reflectionParams[1]->getType();

assert($reflectionType1 instanceof ReflectionNamedType);
echo $reflectionType1->getName(), PHP_EOL;
var_dump($reflectionType2);
?>
```

The above example will output:

    int
    NULL

**Example \#2 <span
class="methodname">ReflectionParameter::getType</span> Usage before PHP
7.1.0**

``` php
<?php
function someFunction(int $param, $param2) {}

$reflectionFunc = new ReflectionFunction('someFunction');
$reflectionParams = $reflectionFunc->getParameters();
$reflectionType1 = $reflectionParams[0]->getType();
$reflectionType2 = $reflectionParams[1]->getType();

echo $reflectionType1, PHP_EOL;
var_dump($reflectionType2);
?>
```

Output of the above example in PHP 7.0:

    int
    NULL

### See Also

-   <span class="methodname">ReflectionParameter::hasType</span>
-   <span class="methodname">ReflectionType::\_\_toString</span>

ReflectionParameter::hasType
============================

Checks if parameter has a type

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ReflectionParameter::hasType</span> ( <span
class="methodparam">void</span> )

Checks if the parameter has a type associated with it.

### Parameters

This function has no parameters.

### Return Values

**`TRUE`** if a type is specified, **`FALSE`** otherwise.

### Examples

**Example \#1 <span
class="methodname">ReflectionParameter::hasType</span> example**

``` php
<?php
function someFunction(string $param, $param2 = null) {}

$reflectionFunc = new ReflectionFunction('someFunction');
$reflectionParams = $reflectionFunc->getParameters();

var_dump($reflectionParams[0]->hasType());
var_dump($reflectionParams[1]->hasType());
```

The above example will output something similar to:

    bool(true)
    bool(false)

### See Also

-   <span class="methodname">ReflectionParameter::getType</span>

ReflectionParameter::isArray
============================

Checks if parameter expects an array

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ReflectionParameter::isArray</span> ( <span
class="methodparam">void</span> )

Checks if the parameter expects an array.

### Parameters

This function has no parameters.

### Return Values

**`TRUE`** if an <span class="type">array</span> is expected,
**`FALSE`** otherwise.

### See Also

-   <span class="methodname">ReflectionParameter::isOptional</span>

ReflectionParameter::isCallable
===============================

Returns whether parameter MUST be callable

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ReflectionParameter::isCallable</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

Returns **`TRUE`** if the parameter is <span
class="type">callable</span>, **`FALSE`** if it is not or **`NULL`** on
failure.

ReflectionParameter::isDefaultValueAvailable
============================================

Checks if a default value is available

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span
class="methodname">ReflectionParameter::isDefaultValueAvailable</span> (
<span class="methodparam">void</span> )

Checks if a default value for the parameter is available.

### Parameters

This function has no parameters.

### Return Values

**`TRUE`** if a default value is available, otherwise **`FALSE`**

### See Also

-   <span class="methodname">ReflectionParameter::getDefaultValue</span>
-   <span
    class="methodname">ReflectionParameter::isDefaultValueConstant</span>
-   <span class="methodname">ReflectionParameter::getName</span>

ReflectionParameter::isDefaultValueConstant
===========================================

Returns whether the default value of this parameter is a constant

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span
class="methodname">ReflectionParameter::isDefaultValueConstant</span> (
<span class="methodparam">void</span> )

Returns whether the default value of this parameter is a constant.

### Parameters

This function has no parameters.

### Return Values

Returns **`TRUE`** if the default value is constant, and **`FALSE`**
otherwise.

### See Also

-   <span
    class="methodname">ReflectionParameter::getDefaultValueConstantName</span>
-   <span
    class="methodname">ReflectionParameter::isDefaultValueAvailable</span>

ReflectionParameter::isOptional
===============================

Checks if optional

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ReflectionParameter::isOptional</span> ( <span
class="methodparam">void</span> )

Checks if the parameter is optional.

### Parameters

This function has no parameters.

### Return Values

**`TRUE`** if the parameter is optional, otherwise **`FALSE`**

### See Also

-   <span class="methodname">ReflectionParameter::getName</span>

ReflectionParameter::isPassedByReference
========================================

Checks if passed by reference

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ReflectionParameter::isPassedByReference</span>
( <span class="methodparam">void</span> )

Checks if the parameter is passed in by reference.

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

**`TRUE`** if the parameter is passed in by reference, otherwise
**`FALSE`**

### See Also

-   <span class="methodname">ReflectionParameter::getName</span>

ReflectionParameter::isVariadic
===============================

Checks if the parameter is variadic

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ReflectionParameter::isVariadic</span> ( <span
class="methodparam">void</span> )

Checks if the parameter was declared as a
<a href="/functions/arguments.html#functions.variable-arg-list" class="link">variadic parameter</a>.

### Parameters

This function has no parameters.

### Return Values

Returns **`TRUE`** if the parameter is variadic, otherwise **`FALSE`**.

ReflectionParameter::\_\_toString
=================================

To string

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">ReflectionParameter::\_\_toString</span> (
<span class="methodparam">void</span> )

To string.

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

### See Also

-   <span class="methodname">ReflectionParameter::export</span>
-   <a href="/language/oop5/magic.html#object.tostring" class="link">__toString()</a>

Introduction
------------

The <span class="classname">ReflectionProperty</span> class reports
information about class properties.

Class synopsis
--------------

**ReflectionProperty**

<span class="ooclass"> class **ReflectionProperty** </span> <span
class="oointerface">implements <span
class="interfacename">Reflector</span> </span> {

/\* Constants \*/

<span class="modifier">const</span> <span class="type">int</span>
`ReflectionProperty::IS_STATIC` <span class="initializer"> = 1</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`ReflectionProperty::IS_PUBLIC` <span class="initializer"> = 256</span>
;

<span class="modifier">const</span> <span class="type">int</span>
`ReflectionProperty::IS_PROTECTED` <span class="initializer"> =
512</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`ReflectionProperty::IS_PRIVATE` <span class="initializer"> =
1024</span> ;

/\* Properties \*/

<span class="modifier">public</span> `$name` ;

<span class="modifier">public</span> `$class` ;

/\* Methods \*/

<span class="modifier">final</span> <span
class="modifier">private</span> <span class="type">void</span> <span
class="methodname">\_\_clone</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> ( <span
class="methodparam"><span class="type">mixed</span> `$class`</span> ,
<span class="methodparam"><span class="type">string</span>
`$name`</span> )

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">string</span> <span
class="methodname">export</span> ( <span class="methodparam"><span
class="type">mixed</span> `$class`</span> , <span
class="methodparam"><span class="type">string</span> `$name`</span> \[,
<span class="methodparam"><span class="type">bool</span>
`$return`</span> \] )

<span class="modifier">public</span> <span
class="type">ReflectionClass</span> <span
class="methodname">getDeclaringClass</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">getDefaultValue</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getDocComment</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getModifiers</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getName</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type"><span
class="type">ReflectionType</span><span class="type">null</span></span>
<span class="methodname">getType</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">getValue</span> (\[ <span
class="methodparam"><span class="type">object</span> `$object`</span> \]
)

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">hasDefaultValue</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">hasType</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">isDefault</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">isInitialized</span> (\[ <span
class="methodparam"><span class="type">object</span> `$object`</span> \]
)

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">isPrivate</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">isProtected</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">isPublic</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">isStatic</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">setAccessible</span> ( <span
class="methodparam"><span class="type">bool</span> `$accessible`</span>
)

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">setValue</span> ( <span
class="methodparam"><span class="type">object</span> `$object`</span> ,
<span class="methodparam"><span class="type">mixed</span>
`$value`</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">\_\_toString</span> ( <span
class="methodparam">void</span> )

}

Properties
----------

`name`  
Name of the property. Read-only, throws <span
class="classname">ReflectionException</span> in attempt to write.

`class`  
Name of the class where the property is defined. Read-only, throws <span
class="classname">ReflectionException</span> in attempt to write.

Predefined Constants
--------------------

ReflectionProperty Modifiers
----------------------------

**`ReflectionProperty::IS_STATIC`**  
Indicates <a href="/language/oop5/static.html" class="link">static</a>
properties.

**`ReflectionProperty::IS_PUBLIC`**  
Indicates
<a href="/language/oop5/visibility.html" class="link">public</a>
properties.

**`ReflectionProperty::IS_PROTECTED`**  
Indicates
<a href="/language/oop5/visibility.html" class="link">protected</a>
properties.

**`ReflectionProperty::IS_PRIVATE`**  
Indicates
<a href="/language/oop5/visibility.html" class="link">private</a>
properties.

ReflectionProperty::\_\_clone
=============================

Clone

### Description

<span class="modifier">final</span> <span
class="modifier">private</span> <span class="type">void</span> <span
class="methodname">ReflectionProperty::\_\_clone</span> ( <span
class="methodparam">void</span> )

Clones.

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

### See Also

-   <span class="methodname">ReflectionProperty::export</span>
-   <a href="/language/oop5/cloning.html" class="link">Object cloning</a>

ReflectionProperty::\_\_construct
=================================

Construct a ReflectionProperty object

### Description

<span class="modifier">public</span> <span
class="methodname">ReflectionProperty::\_\_construct</span> ( <span
class="methodparam"><span class="type">mixed</span> `$class`</span> ,
<span class="methodparam"><span class="type">string</span>
`$name`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`class`  
The class name, that contains the property.

`name`  
The name of the property being reflected.

### Return Values

No value is returned.

### Errors/Exceptions

Trying to get or set private or protected class property's values will
result in an exception being thrown.

### Examples

**Example \#1 <span
class="methodname">ReflectionProperty::\_\_construct</span> example**

``` php
<?php
class Str
{
    public $length  = 5;
}

// Create an instance of the ReflectionProperty class
$prop = new ReflectionProperty('Str', 'length');

// Print out basic information
printf(
    "===> The%s%s%s%s property '%s' (which was %s)\n" .
    "     having the modifiers %s\n",
        $prop->isPublic() ? ' public' : '',
        $prop->isPrivate() ? ' private' : '',
        $prop->isProtected() ? ' protected' : '',
        $prop->isStatic() ? ' static' : '',
        $prop->getName(),
        $prop->isDefault() ? 'declared at compile-time' : 'created at run-time',
        var_export(Reflection::getModifierNames($prop->getModifiers()), 1)
);

// Create an instance of Str
$obj= new Str();

// Get current value
printf("---> Value is: ");
var_dump($prop->getValue($obj));

// Change value
$prop->setValue($obj, 10);
printf("---> Setting value to 10, new value is: ");
var_dump($prop->getValue($obj));

// Dump object
var_dump($obj);
?>
```

The above example will output something similar to:

    ===> The public property 'length' (which was declared at compile-time)
         having the modifiers array (
      0 => 'public',
    )
    ---> Value is: int(5)
    ---> Setting value to 10, new value is: int(10)
    object(Str)#2 (1) {
      ["length"]=>
      int(10)
    }

**Example \#2 Getting value from private and protected properties using
<span class="classname">ReflectionProperty</span> class**

``` php
<?php

class Foo {
    public $x = 1;
    protected $y = 2;
    private $z = 3;
}

$obj = new Foo;

$prop = new ReflectionProperty('Foo', 'y');
$prop->setAccessible(true); /* As of PHP 5.3.0 */
var_dump($prop->getValue($obj)); // int(2)

$prop = new ReflectionProperty('Foo', 'z');
$prop->setAccessible(true); /* As of PHP 5.3.0 */
var_dump($prop->getValue($obj)); // int(2)

?>
```

The above example will output something similar to:

    int(2)
    int(3)

### See Also

-   <span class="methodname">ReflectionProperty::getName</span>
-   <a href="/language/oop5/decon.html#language.oop5.decon.constructor" class="link">Constructors</a>

ReflectionProperty::export
==========================

Export

### Description

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">string</span> <span
class="methodname">ReflectionProperty::export</span> ( <span
class="methodparam"><span class="type">mixed</span> `$class`</span> ,
<span class="methodparam"><span class="type">string</span>
`$name`</span> \[, <span class="methodparam"><span
class="type">bool</span> `$return`</span> \] )

Exports a reflection.

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`argument`  
The reflection to export.

`name`  
The property name.

`return`  
Setting to **`TRUE`** will return the export, as opposed to emitting it.
Setting to **`FALSE`** (the default) will do the opposite.

### Return Values

### See Also

-   <span class="methodname">ReflectionProperty::\_\_toString</span>

ReflectionProperty::getDeclaringClass
=====================================

Gets declaring class

### Description

<span class="modifier">public</span> <span
class="type">ReflectionClass</span> <span
class="methodname">ReflectionProperty::getDeclaringClass</span> ( <span
class="methodparam">void</span> )

Gets the declaring class.

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

A <span class="classname">ReflectionClass</span> object.

### See Also

-   <span class="methodname">ReflectionProperty::getName</span>

ReflectionProperty::getDefaultValue
===================================

Returns the default value declared for a property

### Description

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">ReflectionProperty::getDefaultValue</span> (
<span class="methodparam">void</span> )

Gets the implicit or explicitly declared default value for a property.

### Parameters

This function has no parameters.

### Return Values

The default value if the property has any default value (including
**`NULL`**). If there is no default value, then **`NULL`** is returned.
It is not possible to differentiate between a **`NULL`** default value
and an unitialized typed property. Use <span
class="methodname">ReflectionClass::hasDefaultValue</span> to detect the
difference.

### Examples

**Example \#1 <span
class="methodname">ReflectionClass::getDefaultValue</span> example**

``` php
<?php
class Foo {
    public $bar = 1;
    public ?int $baz;
    public int $boing = 0;
}

$ro = new ReflectionClass(Foo::class);
var_dump($ro->getProperty('bar')->getDefaultValue());
var_dump($ro->getProperty('baz')->getDefaultValue());
var_dump($ro->getProperty('boing')->getDefaultValue());
?>
```

The above example will output:

    int(1)
    NULL
    int(0)

### See Also

-   <span class="methodname">ReflectionProperty::hasDefaultValue</span>

ReflectionProperty::getDocComment
=================================

Gets the property doc comment

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">ReflectionProperty::getDocComment</span> (
<span class="methodparam">void</span> )

Gets the doc comment for a property.

### Parameters

This function has no parameters.

### Return Values

The property doc comment.

### Examples

**Example \#1 <span
class="methodname">ReflectionProperty::getDocComment</span> example**

``` php
<?php
class Str
{
    /**
     * @var int  The length of the string
     */
    public $length = 5;
}

$prop = new ReflectionProperty('Str', 'length');

var_dump($prop->getDocComment());

?>
```

The above example will output something similar to:

    string(53) "/**
         * @var int  The length of the string
         */"

**Example \#2 Multiple property declarations**

If multiple property declarations are preceeded by a single doc comment,
the doc comment refers to the first property only.

``` php
<?php
class Foo
{
    /** @var string */
    public $a, $b;
}
$class = new \ReflectionClass('Foo');
foreach ($class->getProperties() as $property) {
    echo $property->getName() . ': ' . var_export($property->getDocComment(), true) . PHP_EOL;
}
?>
```

The above example will output:

    a: '/** @var string */'
    b: false

### See Also

-   <span class="methodname">ReflectionProperty::getModifiers</span>
-   <span class="methodname">ReflectionProperty::getName</span>
-   <span class="methodname">ReflectionProperty::getValue</span>

ReflectionProperty::getModifiers
================================

Gets the property modifiers

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">ReflectionProperty::getModifiers</span> ( <span
class="methodparam">void</span> )

Gets the modifiers.

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

A numeric representation of the modifiers.

### See Also

-   <span class="methodname">ReflectionProperty::isPrivate</span>
-   <span class="methodname">Reflection::getModifierNames</span>

ReflectionProperty::getName
===========================

Gets property name

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">ReflectionProperty::getName</span> ( <span
class="methodparam">void</span> )

Gets the properties name.

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

The name of the reflected property.

### See Also

-   <span class="methodname">ReflectionProperty::getValue</span>

ReflectionProperty::getType
===========================

Gets a property's type

### Description

<span class="modifier">public</span> <span class="type"><span
class="type">ReflectionType</span><span class="type">null</span></span>
<span class="methodname">ReflectionProperty::getType</span> ( <span
class="methodparam">void</span> )

Gets the associated type of a property.

### Parameters

This function has no parameters.

### Return Values

Returns a <span class="classname">ReflectionType</span> if the property
has a type, and **`NULL`** otherwise.

### Examples

**Example \#1 <span
class="methodname">ReflectionProperty::getType</span> example**

``` php
<?php
class User
{
    public string $name;
}

$rp = new ReflectionProperty('User', 'name');
echo $rp->getType()->getName();
?>
```

The above example will output:

    string

### See Also

-   <span class="methodname">ReflectionProperty::hasType</span>
-   <span class="methodname">ReflectionProperty::isInitialized</span>

ReflectionProperty::getValue
============================

Gets value

### Description

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">ReflectionProperty::getValue</span> (\[ <span
class="methodparam"><span class="type">object</span> `$object`</span> \]
)

Gets the property's value.

### Parameters

`object`  
If the property is non-static an object must be provided to fetch the
property from. If you want to fetch the default property without
providing an object use <span
class="methodname">ReflectionClass::getDefaultProperties</span> instead.

### Return Values

The current value of the property.

### Errors/Exceptions

Throws a <span class="classname">ReflectionException</span> if the
property is inaccessible. You can make a protected or private property
accessible using <span
class="methodname">ReflectionProperty::setAccessible</span>.

### Examples

**Example \#1 <span
class="methodname">ReflectionProperty::getValue</span> example**

``` php
<?php
class Foo {
    public static $staticProperty = 'foobar';
    
    public $property = 'barfoo';
    protected $privateProperty = 'foofoo';
}

$reflectionClass = new ReflectionClass('Foo');

var_dump($reflectionClass->getProperty('staticProperty')->getValue());
var_dump($reflectionClass->getProperty('property')->getValue(new Foo));

$reflectionProperty = $reflectionClass->getProperty('privateProperty');
$reflectionProperty->setAccessible(true);
var_dump($reflectionProperty->getValue(new Foo));
?>
```

The above example will output:

    string(6) "foobar"
    string(6) "barfoo"
    string(6) "foofoo"

### See Also

-   <span class="methodname">ReflectionProperty::setValue</span>
-   <span class="methodname">ReflectionProperty::setAccessible</span>
-   <span
    class="methodname">ReflectionClass::getDefaultProperties</span>
-   <span
    class="methodname">ReflectionClass::getStaticPropertyValue</span>

ReflectionProperty::hasDefaultValue
===================================

Checks if property has a default value declared

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ReflectionProperty::hasDefaultValue</span> (
<span class="methodparam">void</span> )

Checks whether the property was declared with a default value, including
an implicit **`NULL`** default value. Only returns **`FALSE`** for typed
properties without default value (or dynamic properties).

### Parameters

This function has no parameters.

### Return Values

If the property has any default value (including **`NULL`**) **`TRUE`**
is returned; if the property is typed without a default value declared
or is a dynamic property, **`FALSE`** is returned.

### Examples

**Example \#1 <span
class="methodname">ReflectionClass::hasDefaultValue</span> example**

``` php
<?php
class Foo {
    public $bar;
    public ?int $baz;
    public int $boing;
}

$ro = new ReflectionClass(Foo::class);
var_dump($ro->getProperty('bar')->hasDefaultValue());
var_dump($ro->getProperty('baz')->hasDefaultValue());
var_dump($ro->getProperty('boing')->hasDefaultValue());
?>
```

The above example will output:

    bool(true)
    bool(false)
    bool(false)

### See Also

-   <span class="methodname">ReflectionProperty::getDefaultValue</span>

ReflectionProperty::hasType
===========================

Checks if property has a type

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ReflectionProperty::hasType</span> ( <span
class="methodparam">void</span> )

Checks if the property has a type associated with it.

### Parameters

This function has no parameters.

### Return Values

**`TRUE`** if a type is specified, **`FALSE`** otherwise.

### Examples

**Example \#1 <span
class="methodname">ReflectionProperty::hasType</span> example**

``` php
<?php
class User
{
    public string $name;
}

$rp = new ReflectionProperty('User', 'name');
var_dump($rp->hasType());
?>
```

The above example will output:

    bool(true)

### See Also

-   <span class="methodname">ReflectionProperty::getType</span>
-   <span class="methodname">ReflectionProperty::isInitialized</span>

ReflectionProperty::isDefault
=============================

Checks if property is a default property

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ReflectionProperty::isDefault</span> ( <span
class="methodparam">void</span> )

Checks whether the property was declared at compile-time, or whether the
property was dynamically declared at run-time.

### Parameters

This function has no parameters.

### Return Values

**`TRUE`** if the property was declared at compile-time, or **`FALSE`**
if it was created at run-time.

### Examples

**Example \#1 <span class="methodname">ReflectionClass::isDefault</span>
example**

``` php
<?php
class Foo {
    public $bar;
}

$o = new Foo();
$o->bar = 42;
$o->baz = 42;

$ro = new ReflectionObject($o);
var_dump($ro->getProperty('bar')->isDefault());
var_dump($ro->getProperty('baz')->isDefault());
?>
```

The above example will output:

    bool(true)
    bool(false)

### See Also

-   <span class="methodname">ReflectionProperty::getValue</span>

ReflectionProperty::isInitialized
=================================

Checks whether a property is initialized

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ReflectionProperty::isInitialized</span> (\[
<span class="methodparam"><span class="type">object</span>
`$object`</span> \] )

Checks whether a property is initialized.

### Parameters

`object`  
If the property is non-static an object must be provided to fetch the
property from.

### Return Values

Returns **`FALSE`** for typed properties prior to initialization, and
for properties that have been explicitly <span
class="function">unset</span>. For all other properties **`TRUE`** will
be returned.

### Errors/Exceptions

Throws a <span class="classname">ReflectionException</span> if the
property is inaccessible. You can make a protected or private property
accessible using <span
class="methodname">ReflectionProperty::setAccessible</span>.

### Examples

**Example \#1 <span
class="methodname">ReflectionProperty::isInitialized</span> example**

``` php
<?php
class User
{
    public string $name;
}

$rp = new ReflectionProperty('User', 'name');
$user = new User;
var_dump($rp->isInitialized($user));
$user->name = 'Nikita';
var_dump($rp->isInitialized($user));
?>
```

The above example will output:

    bool(false)
    bool(true)

### See Also

-   <span class="methodname">ReflectionProperty::hasType</span>

ReflectionProperty::isPrivate
=============================

Checks if property is private

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ReflectionProperty::isPrivate</span> ( <span
class="methodparam">void</span> )

Checks whether the property is private.

### Parameters

This function has no parameters.

### Return Values

**`TRUE`** if the property is private, **`FALSE`** otherwise.

### See Also

-   <span class="methodname">ReflectionProperty::isPublic</span>
-   <span class="methodname">ReflectionProperty::isProtected</span>
-   <span class="methodname">ReflectionProperty::isStatic</span>

ReflectionProperty::isProtected
===============================

Checks if property is protected

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ReflectionProperty::isProtected</span> ( <span
class="methodparam">void</span> )

Checks whether the property is protected.

### Parameters

This function has no parameters.

### Return Values

**`TRUE`** if the property is protected, **`FALSE`** otherwise.

### See Also

-   <span class="methodname">ReflectionProperty::isPublic</span>
-   <span class="methodname">ReflectionProperty::isPrivate</span>
-   <span class="methodname">ReflectionProperty::isStatic</span>

ReflectionProperty::isPublic
============================

Checks if property is public

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ReflectionProperty::isPublic</span> ( <span
class="methodparam">void</span> )

Checks whether the property is public.

### Parameters

This function has no parameters.

### Return Values

**`TRUE`** if the property is public, **`FALSE`** otherwise.

### See Also

-   <span class="methodname">ReflectionProperty::isProtected</span>
-   <span class="methodname">ReflectionProperty::isPrivate</span>
-   <span class="methodname">ReflectionProperty::isStatic</span>

ReflectionProperty::isStatic
============================

Checks if property is static

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ReflectionProperty::isStatic</span> ( <span
class="methodparam">void</span> )

Checks whether the property is static.

### Parameters

This function has no parameters.

### Return Values

**`TRUE`** if the property is static, **`FALSE`** otherwise.

### See Also

-   <span class="methodname">ReflectionProperty::isPublic</span>
-   <span class="methodname">ReflectionProperty::isProtected</span>
-   <span class="methodname">ReflectionProperty::isPrivate</span>

ReflectionProperty::setAccessible
=================================

Set property accessibility

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">ReflectionProperty::setAccessible</span> (
<span class="methodparam"><span class="type">bool</span>
`$accessible`</span> )

Sets a property to be accessible. For example, it may allow protected
and private properties to be accessed.

### Parameters

`accessible`  
**`TRUE`** to allow accessibility, or **`FALSE`**.

### Return Values

No value is returned.

### See Also

-   <span class="methodname">ReflectionProperty::isPrivate</span>
-   <span class="methodname">ReflectionProperty::isProtected</span>

ReflectionProperty::setValue
============================

Set property value

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">ReflectionProperty::setValue</span> ( <span
class="methodparam"><span class="type">object</span> `$object`</span> ,
<span class="methodparam"><span class="type">mixed</span>
`$value`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">ReflectionProperty::setValue</span> ( <span
class="methodparam"><span class="type">mixed</span> `$value`</span> )

Sets (changes) the property's value.

### Parameters

`object`  
If the property is non-static an object must be provided to change the
property on. If the property is static this parameter is left out and
only `value` needs to be provided.

`value`  
The new value.

### Return Values

No value is returned.

### Errors/Exceptions

Throws a <span class="classname">ReflectionException</span> if the
property is inaccessible. You can make a protected or private property
accessible using <span
class="methodname">ReflectionProperty::setAccessible</span>.

### Examples

**Example \#1 <span
class="methodname">ReflectionProperty::setValue</span> example**

``` php
<?php
class Foo {
    public static $staticProperty;
    
    public $property;
    protected $privateProperty;
}

$reflectionClass = new ReflectionClass('Foo');

$reflectionClass->getProperty('staticProperty')->setValue('foo');
var_dump(Foo::$staticProperty);

$foo = new Foo;

$reflectionClass->getProperty('property')->setValue($foo, 'bar');
var_dump($foo->property);

$reflectionProperty = $reflectionClass->getProperty('privateProperty');
$reflectionProperty->setAccessible(true);
$reflectionProperty->setValue($foo, 'foobar');
var_dump($reflectionProperty->getValue($foo));
?>
```

The above example will output:

    string(3) "foo"
    string(3) "bar"
    string(6) "foobar"

### See Also

-   <span class="methodname">ReflectionProperty::getValue</span>
-   <span class="methodname">ReflectionProperty::setAccessible</span>
-   <span
    class="methodname">ReflectionClass::setStaticPropertyValue</span>

ReflectionProperty::\_\_toString
================================

To string

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">ReflectionProperty::\_\_toString</span> ( <span
class="methodparam">void</span> )

To string.

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

### See Also

-   <a href="/language/oop5/magic.html#object.tostring" class="link">__toString()</a>

Introduction
------------

The <span class="classname">ReflectionType</span> class reports
information about a function's return type.

Class synopsis
--------------

**ReflectionType**

<span class="ooclass"> class **ReflectionType** </span> {

/\* Methods \*/

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">allowsNull</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">isBuiltin</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">\_\_toString</span> ( <span
class="methodparam">void</span> )

}

ReflectionType::allowsNull
==========================

Checks if null is allowed

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ReflectionType::allowsNull</span> ( <span
class="methodparam">void</span> )

Checks whether the parameter allows **`NULL`**.

### Parameters

This function has no parameters.

### Return Values

**`TRUE`** if **`NULL`** is allowed, otherwise **`FALSE`**

### Examples

**Example \#1 <span class="methodname">ReflectionType::allowsNull</span>
example**

``` php
<?php
function someFunction(string $param, StdClass $param2 = null) {}

$reflectionFunc = new ReflectionFunction('someFunction');
$reflectionParams = $reflectionFunc->getParameters();

var_dump($reflectionParams[0]->getType()->allowsNull());
var_dump($reflectionParams[1]->getType()->allowsNull());
```

The above example will output something similar to:

    bool(false)
    bool(true)

### See Also

-   <span class="methodname">ReflectionType::isBuiltin</span>
-   <span class="methodname">ReflectionType::\_\_toString</span>
-   <span class="methodname">ReflectionParameter::getType</span>

ReflectionType::isBuiltin
=========================

Checks if it is a built-in type

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ReflectionType::isBuiltin</span> ( <span
class="methodparam">void</span> )

Checks if the type is a built-in type in PHP.

### Parameters

This function has no parameters.

### Return Values

**`TRUE`** if it's a built-in type, otherwise **`FALSE`**

### Examples

**Example \#1 <span class="methodname">ReflectionType::isBuiltin</span>
example**

``` php
<?php
class SomeClass {}

function someFunction(string $param, SomeClass $param2, StdClass $param3) {}

$reflectionFunc = new ReflectionFunction('someFunction');
$reflectionParams = $reflectionFunc->getParameters();

var_dump($reflectionParams[0]->getType()->isBuiltin());
var_dump($reflectionParams[1]->getType()->isBuiltin());
var_dump($reflectionParams[2]->getType()->isBuiltin());
```

The above example will output something similar to:

    bool(true)
    bool(false)
    bool(false)

Note that the <span class="methodname">ReflectionType::isBuiltin</span>
method does not distinguish between internal and custom classes. To make
this distinction, the <span
class="methodname">ReflectionClass::isInternal</span> method should be
used on the returned class name.

### See Also

-   <span class="methodname">ReflectionType::allowsNull</span>
-   <span class="methodname">ReflectionType::\_\_toString</span>
-   <span class="methodname">ReflectionClass::isInternal</span>
-   <span class="methodname">ReflectionParameter::getType</span>

ReflectionType::\_\_toString
============================

To string

**Warning**

This function has been *DEPRECATED* as of PHP 7.1.0. Relying on this
function is highly discouraged.

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">ReflectionType::\_\_toString</span> ( <span
class="methodparam">void</span> )

Gets the parameter type name.

### Parameters

This function has no parameters.

### Return Values

Returns the type of the parameter.

### Examples

**Example \#1 <span
class="methodname">ReflectionType::\_\_toString</span> example**

``` php
<?php
function someFunction(string $param) {}

$reflectionFunc = new ReflectionFunction('someFunction');
$reflectionParam = $reflectionFunc->getParameters()[0];

echo $reflectionParam->getType();
```

The above example will output something similar to:

    string

### Changelog

| Version | Description                                                                       |
|---------|-----------------------------------------------------------------------------------|
| 7.1.0   | <span class="methodname">ReflectionType::\_\_toString</span> has been deprecated. |

### See Also

-   <span class="methodname">ReflectionNamedType::getName</span>
-   <span class="methodname">ReflectionType::allowsNull</span>
-   <span class="methodname">ReflectionType::isBuiltin</span>
-   <span class="methodname">ReflectionParameter::getType</span>

Introduction
------------

The <span class="classname">ReflectionGenerator</span> class reports
information about a generator.

Class synopsis
--------------

**ReflectionGenerator**

<span class="ooclass"> class **ReflectionGenerator** </span> {

/\* Methods \*/

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> ( <span
class="methodparam"><span class="type">Generator</span>
`$generator`</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getExecutingFile</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">Generator</span>
<span class="methodname">getExecutingGenerator</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getExecutingLine</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="type">ReflectionFunctionAbstract</span> <span
class="methodname">getFunction</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">object</span>
<span class="methodname">getThis</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">getTrace</span> (\[ <span
class="methodparam"><span class="type">int</span> `$options`<span
class="initializer"> = DEBUG\_BACKTRACE\_PROVIDE\_OBJECT</span></span>
\] )

}

ReflectionGenerator::\_\_construct
==================================

Constructs a ReflectionGenerator object

### Description

<span class="modifier">public</span> <span
class="methodname">ReflectionGenerator::\_\_construct</span> ( <span
class="methodparam"><span class="type">Generator</span>
`$generator`</span> )

Constructs a <span class="classname">ReflectionGenerator</span> object.

### Parameters

`generator`  
A generator object.

### Return Values

No value is returned.

### Examples

**Example \#1 <span
class="methodname">ReflectionGenerator::\_\_construct</span> example**

``` php
<?php

function gen()
{
    yield 1;
}

$gen = gen();

$reflectionGen = new ReflectionGenerator($gen);

echo <<< output
{$reflectionGen->getFunction()->name}
Line: {$reflectionGen->getExecutingLine()}
File: {$reflectionGen->getExecutingFile()}
output;
```

The above example will output something similar to:

    gen
    Line: 5
    File: /path/to/file/example.php

### See Also

-   <span class="methodname">ReflectionGenerator::getFunction</span>
-   <span
    class="methodname">ReflectionGenerator::getExecutingLine</span>
-   <span
    class="methodname">ReflectionGenerator::getExecutingFile</span>

ReflectionGenerator::getExecutingFile
=====================================

Gets the file name of the currently executing generator

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">ReflectionGenerator::getExecutingFile</span> (
<span class="methodparam">void</span> )

Get the full path and file name of the currently executing generator.

### Parameters

This function has no parameters.

### Return Values

Returns the full path and file name of the currently executing
generator.

### Examples

**Example \#1 <span
class="methodname">ReflectionGenerator::getExecutingFile</span>
example**

``` php
<?php

class GenExample
{
    public function gen()
    {
        yield 1;
    }
}

$gen = (new GenExample)->gen();

$reflectionGen = new ReflectionGenerator($gen);

echo "File: {$reflectionGen->getExecutingFile()}";
```

The above example will output something similar to:

    File: /path/to/file/example.php

### See Also

-   <span
    class="methodname">ReflectionGenerator::getExecutingLine</span>
-   <span
    class="methodname">ReflectionGenerator::getExecutingGenerator</span>

ReflectionGenerator::getExecutingGenerator
==========================================

Gets the executing <span class="classname">Generator</span> object

### Description

<span class="modifier">public</span> <span class="type">Generator</span>
<span
class="methodname">ReflectionGenerator::getExecutingGenerator</span> (
<span class="methodparam">void</span> )

Get the executing <span class="classname">Generator</span> object

### Parameters

This function has no parameters.

### Return Values

Returns the currently executing <span class="classname">Generator</span>
object.

### Examples

**Example \#1 <span
class="methodname">ReflectionGenerator::getExecutingGenerator</span>
example**

``` php
<?php

class GenExample
{
    public function gen()
    {
        yield 1;
    }
}

$gen = (new GenExample)->gen();

$reflectionGen = new ReflectionGenerator($gen);

$gen2 = $reflectionGen->getExecutingGenerator();

var_dump($gen2 === $gen);
var_dump($gen2->current());
```

The above example will output something similar to:

    bool(true)
    int(1);

### See Also

-   <span
    class="methodname">ReflectionGenerator::getExecutingLine</span>
-   <span
    class="methodname">ReflectionGenerator::getExecutingFile</span>

ReflectionGenerator::getExecutingLine
=====================================

Gets the currently executing line of the generator

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">ReflectionGenerator::getExecutingLine</span> ( <span
class="methodparam">void</span> )

Get the currently executing line number of the generator.

### Parameters

This function has no parameters.

### Return Values

Returns the line number of the currently executing statement in the
generator.

### Examples

**Example \#1 <span
class="methodname">ReflectionGenerator::getExecutingLine</span>
example**

``` php
<?php

class GenExample
{
    public function gen()
    {
        yield 1;
    }
}

$gen = (new GenExample)->gen();

$reflectionGen = new ReflectionGenerator($gen);

echo "Line: {$reflectionGen->getExecutingLine()}";
```

The above example will output something similar to:

    Line: 7

### See Also

-   <span
    class="methodname">ReflectionGenerator::getExecutingGenerator</span>
-   <span
    class="methodname">ReflectionGenerator::getExecutingFile</span>

ReflectionGenerator::getFunction
================================

Gets the function name of the generator

### Description

<span class="modifier">public</span> <span
class="type">ReflectionFunctionAbstract</span> <span
class="methodname">ReflectionGenerator::getFunction</span> ( <span
class="methodparam">void</span> )

Enables the function name of the generator to be obtained by returning a
class derived from <span
class="classname">ReflectionFunctionAbstract</span>.

### Parameters

This function has no parameters.

### Return Values

Returns a <span class="classname">ReflectionFunctionAbstract</span>
class. This will be <span class="classname">ReflectionFunction</span>
for functions, or <span class="classname">ReflectionMethod</span> for
methods.

### Examples

**Example \#1 <span
class="methodname">ReflectionGenerator::getFunction</span> example**

``` php
<?php

function gen()
{
    yield 1;
}

$gen = gen();

$reflectionGen = new ReflectionGenerator($gen);

var_dump($reflectionGen->getFunction());
```

The above example will output something similar to:

    object(ReflectionFunction)#3 (1) {
      ["name"]=>
      string(3) "gen"
    }

### See Also

-   <span class="methodname">ReflectionGenerator::getThis</span>
-   <span class="methodname">ReflectionGenerator::getTrace</span>

ReflectionGenerator::getThis
============================

Gets the *$this* value of the generator

### Description

<span class="modifier">public</span> <span class="type">object</span>
<span class="methodname">ReflectionGenerator::getThis</span> ( <span
class="methodparam">void</span> )

Get the *$this* value that the generator has access to.

### Parameters

This function has no parameters.

### Return Values

Returns the *$this* value, or **`NULL`** if the generator was not
created in a class context.

### Examples

**Example \#1 <span
class="methodname">ReflectionGenerator::getThis</span> example**

``` php
<?php

class GenExample
{
    public function gen()
    {
        yield 1;
    }
}

$gen = (new GenExample)->gen();

$reflectionGen = new ReflectionGenerator($gen);

var_dump($reflectionGen->getThis());
```

The above example will output something similar to:

    object(GenExample)#3 (0) {
    }

### See Also

-   <span class="methodname">ReflectionGenerator::getFunction</span>
-   <span class="methodname">ReflectionGenerator::getTrace</span>

ReflectionGenerator::getTrace
=============================

Gets the trace of the executing generator

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">ReflectionGenerator::getTrace</span> (\[ <span
class="methodparam"><span class="type">int</span> `$options`<span
class="initializer"> = DEBUG\_BACKTRACE\_PROVIDE\_OBJECT</span></span>
\] )

Get the trace of the currently executing generator.

### Parameters

`options`  
The value of `options` can be any of the following flags.

| Option                               | Description                                                              |
|--------------------------------------|--------------------------------------------------------------------------|
| **`DEBUG_BACKTRACE_PROVIDE_OBJECT`** | Default.                                                                 |
| **`DEBUG_BACKTRACE_IGNORE_ARGS`**    | Don't include the argument information for functions in the stack trace. |

### Return Values

Returns the trace of the currently executing generator.

### Examples

**Example \#1 <span
class="methodname">ReflectionGenerator::getTrace</span> example**

``` php
<?php
function foo() {
    yield 1;
}

function bar()
{
    yield from foo();
}

function baz()
{
    yield from bar();
}

$gen = baz();
$gen->valid(); // start the generator

var_dump((new ReflectionGenerator($gen))->getTrace());
```

The above example will output something similar to:

    array(2) {
      [0]=>
      array(4) {
        ["file"]=>
        string(18) "example.php"
        ["line"]=>
        int(8)
        ["function"]=>
        string(3) "foo"
        ["args"]=>
        array(0) {
        }
      }
      [1]=>
      array(4) {
        ["file"]=>
        string(18) "example.php"
        ["line"]=>
        int(12)
        ["function"]=>
        string(3) "bar"
        ["args"]=>
        array(0) {
        }
      }
    }

### See Also

-   <span class="methodname">ReflectionGenerator::getFunction</span>
-   <span class="methodname">ReflectionGenerator::getThis</span>

Introduction
------------

The <span class="classname">ReflectionReference</span> class provides
information about a reference.

Class synopsis
--------------

**ReflectionReference**

<span class="ooclass"> <span class="modifier">final</span> class
**ReflectionReference** </span> {

/\* Methods \*/

<span class="modifier">public</span> <span
class="modifier">static</span> <span
class="type">ReflectionReference</span> <span
class="methodname">fromArrayElement</span> ( <span
class="methodparam"><span class="type">array</span> `$array`</span> ,
<span class="methodparam"><span class="type">mixed</span> `$key`</span>
)

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">getId</span> ( <span
class="methodparam">void</span> )

}

ReflectionReference::fromArrayElement
=====================================

Create a ReflectionReference from an array element

### Description

<span class="modifier">public</span> <span
class="modifier">static</span> <span
class="type">ReflectionReference</span> <span
class="methodname">ReflectionReference::fromArrayElement</span> ( <span
class="methodparam"><span class="type">array</span> `$array`</span> ,
<span class="methodparam"><span class="type">mixed</span> `$key`</span>
)

Creates a <span class="classname">ReflectionReference</span> from an
array element.

### Parameters

`array`  
The <span class="type">array</span> which contains the potential
reference.

`key`  
The key; either an <span class="type">int</span> or a <span
class="type">string</span>.

### Return Values

Returns a <span class="classname">ReflectionReference </span> instance
if *$array\[$key\]* is a reference, or **`NULL`** otherwise.

### Errors/Exceptions

If `array` is not an <span class="type">array</span>, or `key` is not an
<span class="type">int</span> or <span class="type">string</span>, a
<span class="classname">TypeError</span> is thrown. If *$array\[$key\]*
does not exist, a <span class="classname">ReflectionException</span> is
thrown.

ReflectionReference::getId
==========================

Get unique ID of a reference

### Description

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">ReflectionReference::getId</span> ( <span
class="methodparam">void</span> )

Returns an ID which is unique for the reference for the lifetime of that
reference. This ID can be used to compare references for equality, or to
maintain a map of known references.

### Parameters

This function has no parameters.

### Return Values

Returns an <span class="type">int</span> or <span
class="type">string</span> of unspecified format.

### Examples

**Example \#1 Basic <span
class="methodname">ReflectionReference::getId</span> usage**

``` php
<?php
$val1 = 'foo';
$val2 = 'bar';
$arr = [&$val1, &$val2, &$val1];

$rr1 = ReflectionReference::fromArrayElement($arr, 0);
$rr2 = ReflectionReference::fromArrayElement($arr, 1);
$rr3 = ReflectionReference::fromArrayElement($arr, 2);

var_dump($rr1->getId() === $rr2->getId());
var_dump($rr1->getId() === $rr3->getId());
?>
```

The above example will output:

    bool(false)
    bool(true)

Introduction
------------

<span class="classname">Reflector</span> is an interface implemented by
all exportable Reflection classes.

Class synopsis
--------------

**Reflector**

<span class="ooclass"> class **Reflector** </span> {

/\* Methods \*/

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">string</span> <span
class="methodname">export</span> ( <span class="methodparam">void</span>
)

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">\_\_toString</span> ( <span
class="methodparam">void</span> )

}

Reflector::export
=================

Exports

**Warning**

This function has been *DEPRECATED* as of PHP 7.4.0. Relying on this
function is highly discouraged.

### Description

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">string</span> <span
class="methodname">Reflector::export</span> ( <span
class="methodparam">void</span> )

Exports.

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

### See Also

-   <span class="methodname">Reflection::\_\_toString</span>

Reflector::\_\_toString
=======================

To string

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">Reflector::\_\_toString</span> ( <span
class="methodparam">void</span> )

To string.

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

### See Also

-   <span class="methodname">ReflectionProperty::export</span>
-   <a href="/language/oop5/magic.html#object.tostring" class="link">__toString()</a>

Introduction
------------

The ReflectionException class.

Class synopsis
--------------

**ReflectionException**

<span class="ooclass"> class **ReflectionException** </span> <span
class="ooclass"> <span class="modifier">extends</span> **Exception**
</span> {

/\* Properties \*/

<span class="modifier">protected</span> <span class="type">string</span>
`$message` ;

<span class="modifier">protected</span> <span class="type">int</span>
`$code` ;

<span class="modifier">protected</span> <span class="type">string</span>
`$file` ;

<span class="modifier">protected</span> <span class="type">int</span>
`$line` ;

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
