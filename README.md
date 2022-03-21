# PDFF : PHP Document File Format

This is a repository for the PDFF files. 

## Work In Progress 

There is some early results here, more will come as time permits.

## Content

The PDFF folder contains 3 sub-folders : 
+ ext : PHP extensions, extracted from pecl and the standard distribution, compiled on Debian. 
+ vcs : PHP packages, when available as a single repository. For example, concrete5, or slim PHP.
+ packagist : some PHP packages, listed from packagist.org, with the same naming scheme.

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
                 + __parameters__ : array of parameters
                 + `totalParameters` : count of all parameters (int)
                 + `optionalParameters` : count of optional parameters (int)
                 + `variadic` : is it a variadic function, which means one of the parameter is variadic
                 + `attributes` : array of attributes
                 + `phpdoc` : array fo phpdoc
         + `classes` : array of classes
         + `traits` : array of traits
         + `interfaces` : array of interfaces
         + `enums` : array of enums

