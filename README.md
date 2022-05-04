# PDFF : PHP Document File Format

This is a repository for the PDFF files. 

## Work In Progress 

There is some early results here, more will come as time permits.

## Content

The PDFF folder contains 3 sub-folders : 
+ [ext](ext.md) : PHP extensions, extracted from pecl and the standard distribution, compiled on Debian. 
+ [frameworks](vcs.md) : PHP packages, when available as a single repository. For example, concrete5, or slim PHP.
+ [packagist](packagist.md) : some PHP packages, listed from packagist.org, with the same naming scheme. Not all, because there are too many. 

Only major and middle versions are provided currently. So, vcs/cakephp/4.3.0.pdff represents the last availble 4.3.* version. 

All files are in compact JSON notation. 

## Structure of the pdff file : 

The PDFF file has the following structure : 

+ Root
    + __versions__ (or star `*`)
       + __namespaces__, including global root \\
           + `constants`
               + __constant name__
                   + `name`
                   + `value`
                   + `phpdoc`
                   + `expression` : is the value a PHP expression (true) or a literal (false)
          + `functions`
              + __function name__
                 + `name`
                 + `returntype` : "one" for a single return type, including the absence of type; "or" for union type and "and" for intersectional types. 
                 + `returntypehints` : array for fully qualified names of types
                 + __parameters__
                     + `name`
                     + `rank` : startign a index 0
                     + `variadic`
                     + `reference`
                     + `default` 
                     + `hasDefault` : boolean, meaning that this parameter has a default value or not. 
                     + `expression` : is the default value a PHP expression (true) or a literal (false)
                     + `typehinttype` : "one" for a single return type, including the absence of type; "or" for union type and "and" for intersectional types. 
                     + __typehints__ : an array
                         +  `typehint` : the typehint's fully qualified name, or one of the PHP native types (string, never, callable...)
                     + `attributes` : array of strings
                     + `phpdoc` : array of strings
                 + `totalParameters` : count of all parameters (int)
                 + `optionalParameters` : count of optional parameters (int)
                 + `variadic` : is it a variadic function, which means one of the parameter is variadic
                 + `attributes`
                      + `attribute` : attribute's expression
                 + `phpdoc` : array fo phpdoc strings
          + `classes`
              + __constants__
                  + __constant name__
                      + `name`
                      + `value`
                      + `phpdoc`
                      + `final`
                      + `visibility` : one among 'private', 'public', 'protected', 'none'
                      + `expression` : is the value a PHP expression (true) or a literal (false)                         
                      + `attributes`
                            + `attribute` : attribute's expression
                      + `phpdoc` : array fo phpdoc strings
                 + __methods__
                     + `name`
                     + `returntype` : "one" for a single return type, including the absence of type; "or" for union type and "and" for intersectional types. 
                     + `returntypehints` : array for fully qualified names of types
                     + __parameters__
                         + `name`
                         + `rank` : startign a index 0
                         + `visibility` : one among 'private', 'public', 'protected', 'none'
                         + `variadic`
                         + `static`
                         + `reference`
                         + `default` 
                         + `hasDefault` : boolean, meaning that this parameter has a default value or not. 
                         + `expression` : is the default value a PHP expression (true) or a literal (false)
                         + `returntype` : "one" for a single return type, including the absence of type; "or" for union type and "and" for intersectional types. 
                         + __returntypehints__ : an array
                             +  `typehint` : the typehint's fully qualified name, or one of the PHP native types (string, never, callable...)
                         + `attributes` : array of strings
                         + `phpdoc` : array of strings
                         + `totalParameters` : count of all parameters (int)
                         + `optionalParameters` : count of optional parameters (int)
                         + `variadic` : is it a variadic function, which means one of the parameter is variadic
                         + `attributes`
                             + `attribute` : attribute's expression
                         + `phpdoc` : array fo phpdoc strings 
                   + __properties__
                       + `name`
                       + `var` : using the var keyword or not
                       + `static`
                       + `hasDefault`
                       + `init` 
                       + `expression`
                       + `visibility` 
                       + `typehinttype`
                       + `attributes`
                           + `attribute` : attribute's expression
                       + `phpdoc` : array fo phpdoc strings 
         + `traits` : array of traits
             + __methods__
                 + `name`
                 + `returntype` : "one" for a single return type, including the absence of type; "or" for union type and "and" for intersectional types. 
                 + `returntypehints` : array for fully qualified names of types
                 + __parameters__
                     + `name`
                     + `rank` : startign a index 0
                     + `visibility` : one among 'private', 'public', 'protected', 'none'
                     + `variadic`
                     + `static`
                     + `reference`
                     + `default` 
                     + `hasDefault` : boolean, meaning that this parameter has a default value or not. 
                     + `expression` : is the default value a PHP expression (true) or a literal (false)
                     + `returntype` : "one" for a single return type, including the absence of type; "or" for union type and "and" for intersectional types. 
                     + __returntypehints__ : an array
                         +  `typehint` : the typehint's fully qualified name, or one of the PHP native types (string, never, callable...)
                     + `attributes` : array of strings
                     + `phpdoc` : array of strings
                     + `totalParameters` : count of all parameters (int)
                     + `optionalParameters` : count of optional parameters (int)
                     + `variadic` : is it a variadic function, which means one of the parameter is variadic
                     + `attributes`
                         + `attribute` : attribute's expression
                     + `phpdoc` : array fo phpdoc string
                   + __properties__
                       + `name`
                       + `var` : using the var keyword or not
                       + `static`
                       + `hasDefault`
                       + `init` 
                       + `expression`
                       + `visibility` 
                       + `typehinttype`
                       + `attributes`
                           + `attribute` : attribute's expression
                       + `phpdoc` : array fo phpdoc strings
         + `interfaces` : array of interfaces
             + __constants__
                 + __constant name__
                     + `name`
                     + `value`
                     + `phpdoc`
                     + `final`
                     + `visibility` : one among 'private', 'public', 'protected', 'none'
                     + `expression` : is the value a PHP expression (true) or a literal (false)                         
                     + `attributes`
                           + `attribute` : attribute's expression
                     + `phpdoc` : array fo phpdoc strings
                 + __methods__
                     + `name`
                     + `returntype` : "one" for a single return type, including the absence of type; "or" for union type and "and" for intersectional types. 
                     + `returntypehints` : array for fully qualified names of types
                     + __parameters__
                         + `name`
                         + `rank` : startign a index 0
                         + `visibility` : one among 'private', 'public', 'protected', 'none'
                         + `variadic`
                         + `static`
                         + `reference`
                         + `default` 
                         + `hasDefault` : boolean, meaning that this parameter has a default value or not. 
                         + `expression` : is the default value a PHP expression (true) or a literal (false)
                         + `returntype` : "one" for a single return type, including the absence of type; "or" for union type and "and" for intersectional types. 
                         + __returntypehints__ : an array
                                 +  `typehint` : the typehint's fully qualified name, or one of the PHP native types (string, never, callable...)
                         + `attributes` : array of strings
                         + `phpdoc` : array of strings
                     + `totalParameters` : count of all parameters (int)
                     + `optionalParameters` : count of optional parameters (int)
                     + `variadic` : is it a variadic function, which means one of the parameter is variadic
                     + `attributes`
                         + `attribute` : attribute's expression
                     + `phpdoc` : array fo phpdoc strings 
         + `enums` : array of enums
                 + __constants__
                 + __methods__


Know limitations
----------------

+ PDFF do not support conditional structures. In other words, it is not possible to have two definitions for the same FQN. 
+ PDFF do not support dynamic configurations, such as class_alias()

