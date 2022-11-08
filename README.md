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

Please note that these forms of encryption are not extremely secure and should only be used to hinder a person from gaining direct access to data stored in raw text.

## How do I use Krypton?
### Setup
If you are using Visual Studio, you can start by adding Krypton as a project reference. To do this:
1. Go to *Project > Add Project Reference > Browse* then locate the DLL file on your computer.
2. Click OK and wait for Visual Studio to add the reference.
3. In any C# class in the project, add the line '*using Vega.Krypton;*' at the top.
Krypton can now be used.

### Using Encryption Services
Krypton's encryption services are found in Krypton's namesake, the '*Krypton*' class. You can access them by following these steps:
1. Create a new '*KryptonType*' enum. This is used to tell Krypton what encoder you wish it to use.
2. Set your '*KryptonType*' to a value. This can be one of the following: A, L, U, U8 or U32. Each corresponds to a respective encryption type: ASCII, Latin1, Unicode, UTF-8 or UTF-32.
3. Create a new '*Krypton*' object. Make sure to pass in the '*KryptonType*' enum you just created.
4. Call the '*Encode*' method. Make sure to pass a string as the argument. This method will return a string that has been encrypted using your previously selected format.
Note that if you ever want to change the encoding type being used, you can call the '*SwitchType*' method, passing in a '*KryptonType*' enum of the new type you want to use.

### Using Decryption Services
Similarly to the encryption services, Kryption's decryption services are found in Kryption's namesake, the '*Krypton*' class. You can access them by following these steps:
