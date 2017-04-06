# wadlrr ![Build Status](https://travis-ci.com/marcbizal/wadlrr.svg?token=mABEpk1bXrf7VZkfebmt&branch=master) [![Coverage Status](https://coveralls.io/repos/github/marcbizal/wadlrr/badge.svg?branch=master)](https://coveralls.io/github/marcbizal/wadlrr?branch=master)

A Node.js interface for creating, extracting, modifying, and reading LRR WAD files.

## API

<!-- Generated by documentation.js. Update this documentation by updating the source code. -->

### indexOf

This function finds the index of a given path in a WAD file.

**Parameters**

-   `wadMeta` **[Object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object)** any valid WAD metadata object
-   `filePath` **[string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)** the relative or absolute path of a file contained in the WAD

Returns **[Number](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number)** the index that the file was found at

### exists

This function checks if a file exists given path in a WAD file.

**Parameters**

-   `wadMeta` **[Object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object)** any valid WAD metadata object
-   `filePath` **[string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)** the relative path of the file in question

Returns **[Boolean](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean)**

### getObjectFromFile

This function reads data for a given object from an open WAD file.

**Parameters**

-   `fd` **[Number](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number)** file descriptor for the open WAD file
-   `object` **[Object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object)** the object's metadata

Returns **[Promise](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)&lt;[Buffer](https://nodejs.org/api/buffer.html)>** resolves to a buffer containing the object data

### getObjectMeta

This function returns the object metadata at a given path in a WAD file
or throws an error if the file doesn't exist.

**Parameters**

-   `wadMeta` **[Object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object)** any valid WAD metadata object
-   `filePath` **[string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)** the relative path of a file contained in the WAD

Returns **[Object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object)** resolves to the object metadata

### getObject

This function reads a buffer from a given WAD that represents the actual object data.

**Parameters**

-   `wadMeta` **[Object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object)** any valid WAD metadata object
-   `object` **[Object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object)** the object's metadata

Returns **[Promise](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)&lt;[Buffer](https://nodejs.org/api/buffer.html)>** resolves to a buffer containing the object data

### getObjectAtPath

This function reads a buffer that represents object data at a given path.

**Parameters**

-   `wadMeta` **[Object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object)** any valid WAD metadata object
-   `filePath` **[string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)** the object's internal path

Returns **[Promise](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)&lt;[Buffer](https://nodejs.org/api/buffer.html)>** a buffer containing the object data

### getObjectStream

This function gets a read stream for a given object

**Parameters**

-   `wadMeta` **[Object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object)** any valid WAD metadata object
-   `object` **[Object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object)** the object's metadata

Returns **ReadStream** a read stream for the object

### getObjectStreamAtPath

This function gets a stream for object data at a given path.

**Parameters**

-   `wadMeta` **[Object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object)** any valid WAD metadata object
-   `filePath` **[string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)** the object's internal path

Returns **ReadStream** a read stream for the object

### extract

This function extracts all files from a given WAD.

**Parameters**

-   `wadMeta` **[Object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object)** any valid WAD metadata object
-   `outputPath` **[string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)** the base output path

Returns **[Promise](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)** resolves when all files have been extracted

### load

This function parses a WAD file's metadata.

**Parameters**

-   `wadPath` **[string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)** path to the WAD file itself

Returns **[Object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object)** metadata describing the WAD
