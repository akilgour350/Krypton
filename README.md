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

## How do I use Krypton?
### Setup
If you are using Visual Studio, you can start by adding Krypton as a project reference. To do this:
1. Go to *Project > Add Project Reference > Browse* then locate the DLL file on your computer.
2. Click OK and wait for Visual Studio to add the reference.
3. Finally, import the library to a file. If you are using C#, you can do this with the following code: `*using Vega.Krypton;*`
Krypton will now work in the file where it is imported.

### The '*KryptonType*' Enum
To use any of Krypton's features, you will need to create an instance of the '*KryptonType*' enum and pass it in when creating any Krypton classes. To create and configure it, use the following steps:
1. Complete the setup process outlined above. You won't have access to the '*KryptonType*' enum if you don't!
2. Create a new instance of the '*KryptonType*' enum. You can do this with the following line in C#: `*KryptonType kt;*`.
3. Choose the type of encryption you wish to use. This can be done by assigning a value to the newly created enum instance. The values that can be assigned are:
  - A
  - L
  - U
  - U8
  - U32
  Each corresponds to an encryption type, respectively:
  - ASCII
  - Latin1
  - Unicode
  - UTF-8
  - UTF-32
  In C#, the value can be assigned with the following code: `*kt = KryptonType.A*`.
 The enum has now been set up.

### Using Encryption Services
Krypton's encryption services are found in Krypton's namesake, the '*Krypton*' class. You can access them by following these steps:
1. Create a new '*KryptonType*' enum using the above steps, configuring it for the encoder you wish to use.
2. Create a new '*Krypton*' object. Make sure to pass in the '*KryptonType*' enum you just created.
3. Call the '*Encode*' method. Make sure to pass a string as the argument. This method will return a string that has been encrypted using your previously selected format.
Note that if you ever want to change the encoding type being used, you can call the '*SwitchType*' method, passing in a '*KryptonType*' enum of the new type you want to use.

### Using Decryption Services
Similarly to the encryption services, Kryption's decryption services are found in Kryption's namesake, the '*Krypton*' class. You can access them by following these steps:
1. Create a new '*KryptonType*' enum using the above steps, configuring it for the encoder you wish to use.
2. Create a new '*Krypton*' object. Make sure to pass in the '*KryptonType*' enum you just created.
3. Call the '*Decode*' method. Make sure to pass a string as the argument. This method will return a string that has been decrypted using your previously selected format.
Note that if you ever want to change the decoding type being used, you can call the '*SwitchType*' method, passing in a '*KryptonType*' enum of the new type you want to use.

### Using Basic File Handling
If you are looking for file handling with encoding and decoding, refer to the '*Using Encoded File Handling*' section below.
Krypton's basic file handling services are located in the '*UFile*' class. You can access it by doing the following:
1. Create a new '*KryptonType*' enum using the steps outlined above, configuring it to use the encoder/decoder you wish to use.
2. Create a new '*UFile*' class instance, passing in the just created enum.
You now have access to Krypton's basic reading and writing classes.

The '*UFile*' class contains two methods for writing to files.


### Using Encoded File Handling
Krypton's encoded file handling services are located in the '*KFile*' class. If you are looking for file handling without encoding, refer to the '*Using Basic File Handling*' section above.
