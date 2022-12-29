# Krypton

## What is Krypton?
Krypton is a library of methods that can be used for basic file handling, as well as for encrypting and decrypting strings.

## What files can Krypton handle?
Krypton can handle every form of raw text file such as TXT or CSV.

## What encryption does Krypton offer?
Krypton offers basic encryption and decryption using the following formats available through C#'s Encoding class:
- ASCII
- Latin1
- Unicode
- UTF-8
- UTF-32

Please note that these forms of encryption are not extremely secure and should only be used to stop a person from directly accessing a file's data.

## What Documentation is available?
This README file contains the complete documentation for Krypton. However, if you are like me and find Markdown to be a little sore on the eyes, I'm working on adding a documentation page to my website. You can find it [here.](https://akilgour350.github.io/projects/krypton_documentation.html) However, please note the page is still work-in-progress and therefore may be incomplete.



---

## How do I use Krypton?
### Setup
To use Krypton, you must first add the DLL file as a reference. If you are using Visual Studio, you can add a reference by following these steps:
1. Go to `Project > Add Project Reference > Browse` then locate the DLL file on your computer.
2. Click OK and wait for Visual Studio to add the reference.
3. Finally, import the library to a file. If you are using C#, you can do this with the following code: `using Vega.Krypton;`

If you are not using Visual Studio, check your IDE's documentation to see how to add project references. In all IDEs, the final step will be the same.

<br />

### The `KryptonType` Enum
To use any of Krypton's encryption features, you will need to create an instance of the `KryptonType` enum and pass it in when creating most Krypton classes. To create and configure it, use the following steps:
1. Complete the setup process outlined above. You won't have access to the `KryptonType` enum type if you don't!
2. Create a new instance of the `KryptonType` enum. You can do this with the following line in C#: `KryptonType kt;`.
3. Choose the type of encryption you wish to use. This can be done by assigning a value to the newly created enum instance. The values that can be assigned are: `A`, `L`, `U`, `U8` and `U32`. Each corresponded to an encryption type: ASCII, Latin1, Unicode, UTF-8 and UTF-32 respectivly.
In C#, the value can be assigned with the following code: `kt = KryptonType.A;`.

The enum has now been set up.

<br />

### Using Encryption Services
Krypton's encryption services are found in Krypton's namesake, the `Krypton` class. You can access them by following these steps:
1. Create a new `KryptonType` enum using the above steps, configuring it for the encoder you wish to use.
2. Create a new `Krypton` object. Make sure to pass in the `KryptonType` enum you just created.
3. Call the `Encode` method. Make sure to pass a string as the argument. This method will return a string that has been encrypted using your previously selected format.

Note that if you ever want to change the encoding type being used, you can call the `SwitchType` method, passing in a `KryptonType` enum of the new type you want to use.

<br />

### Using Decryption Services
Similarly to the encryption services, Kryption's decryption services are found in Krypton's namesake, the `Krypton` class. You can access them by following these steps:
1. Create a new `KryptonType` enum using the above steps, configuring it for the encoder you wish to use.
2. Create a new `Krypton` object. Make sure to pass in the `KryptonType` enum you just created.
3. Call the `Decode` method. Make sure to pass a string as the argument. This method will return a string that has been decrypted using your previously selected format.

Note that if you ever want to change the decoding type being used, you can call the `SwitchType` method, passing in a `KryptonType` enum of the new type you want to use.

<br />


### Using Encoded File Handling
If you are looking for file handling without encoding and decoding, refer to the '*Using Basic File Handling*' section below. \
Krypton's primary use is in handling files that have been encoded using one of five methods: ASCII, Latin1, Unicode, UTF-8 or UTF-32. It is assumed you know what type of encoding was used in an already encrypted file. Please also note these forms of encryption are not entirely secure, and can be read by programs using Krypton or others utilising similar code. The primary purpose is to make data un-readable to the human eye.

The `KFile` class is used to handle the encryption and decryption of files. You can access it by creating a new instance of the class. In C#, this is done with the following code: `KFile kf = new KFile();` You now have access to Krypton's encrypted file handling capabilities.

<br />

The `KFile` class contains two methods for writing to files:
- `AppendToFile`
- `OverwriteToFile`

Both require three arguments in the following order:
- The directory of the file you wish to write to,
- The text you wish to write to the file,
- A `KryptonType` enum configured to the desired encryption type.

The `AppendToFile` method will encrypyt text, using the chosen encoder, then add it to the end of a file leaving the previous contents intact. \
The `OverwriteToFile` method will erase all text in a file and replace it with the text passed to the method, encrypted using the chosen encoder.

<br />

The `KFile` class also contains two methods for reading encrypted files:
- `ReadFromFile`
- `ListFromFile`

Both require two arguments in the following order:
- The directory of the file you wish to read from,
- A `KryptonType` enum configured to the desired decryption type.

The `ReadFromFile` method will read in text from the specified file, decrypt it using the chosen decoder, then return a string of the decrypted text. \
The `ListFromFile` method will read in text one line at a time into a List object of strings, decrypting each line, then return the List of lines. \
Please note that both of these methods will return *null* if an error is encountered, so it is good practice to check the returned value before using it further on in your code. Details of any errors encountered will be printed to the console.

<br />

### Using Basic File Handling
If you are looking for file handling with encoding and decoding, refer to the '*Using Encoded File Handling*' section above. \
Krypton's basic file handling services are located in the `UFile` class. You can access it by creating a new instance of the `UFile` class. In C#, this is done with the following code: `UFile uf = new UFile();` You now have access to Krypton's basic file handling capabilities.

<br />

The `UFile` class contains two methods for writing to files:
- `AppendToFile`
- `OverwriteToFile`

Both require two strings as arguments in the following order:
1. The directory of the file you wish to write to,
2. The text you wish to write to the file.

The `AppendToFile` method will add text to the end of an existing file, leaving the rest of the file intact. \
The `OverwriteToFile` method will erase all text in a file and replace it with the text passed to the method.

<br />

The `UFile` class also contains two methods for reading from files:
- `ReadFromFile`
- `ListFromFile`

Both require only the directory of the file to be passed in.
Note that if either method throws an error, its details will be written to the console and the method will return *null*. Therefore, it is good practice to check *null* has not been returned before attempting to use the output.

The `ReadFromFile` method will return a string containing all of the text in the file within the given directory. \
The `ListFromFile` method will return a List object of strings, where each item is a line in the file.
