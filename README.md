# Getting started with AWS Lambda Layers for cx_Oracle Python 3.x

A layer is a .zip file archive that contains libraries, a custom runtime, or other dependencies. 
With layers, you can use libraries in your function without needing to include them in your deployment package. you can 
configure your AWS lambda function to pull in additional code and content in form of layers. Layers let you keep your deployment package small, 
which makes development easier. You can avoid errors that can occur when you install and package dependencies with your function code.
For Node.js, Python, and Ruby functions, you can develop your function code in the Lambda console as long as you keep your deployment package under 3 MB.

A lambda function can use up to five layers at a time. The total unzipped size of the function and all layers can't exceed the
unzipped deployment package size limit of 250 MB. You can create layers, or use layers that AWS or an AWS customer has published. Layers support resource-based policies 
for granting layer usage permissions to specific AWS accounts, AWS Organizations, or all accounts. Layers are extracted 
to the /opt directory in the function execution environment. Each runtime looks for libraries in a different location 
under /opt, depending on the language. Structure your layer so that function code can access libraries without additional configuration.

## what we need to create a cx_Oracle layer

cx_Oracle is a Python extension module that enables access to Oracle Database and conforms to the Python database API specification.
cx_Oracle requires Oracle Client libraries. The libraries provide the necessary network connectivity to access an Oracle Database instance. 
They also provide basic and advanced connection management and data features to cx_Oracle.

The cx_Oracle module loads Oracle Client libraries which communicate over Oracle Net to an existing database. 
Oracle Net is not a separate product: it is how the Oracle Client and Oracle Database communicate. cx_Oracle uses the shared library 
loading mechanism available on each supported platform to load the Oracle Client libraries at runtime. It does not need to be rebuilt for different versions of the libraries. 
Since a single cx_Oracle binary can use different client versions and also access multiple database versions, it is important your application is tested in your intended release environments.

##### Note : As the lambda runtime is linux, you have to download the library in linux and package it.




 