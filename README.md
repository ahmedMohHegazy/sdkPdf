# **Ios NfcManager Library Documentation**

Welcome to the comprehensive documentation for utilizing the NfcManager
library, facilitating the reading and writing operations for
IsoDep NFC cards. This library streamlines the process for
developers working on Ios native or React Native applications,
enabling convenient integration of NFC card functionality.

## **Key Features**

-   **Read and Write**: Seamlessly read from and write to
    IsoDep,MifareClassic NFC cards.

-   **Start Nfc Detection**: Initiate NFC detection for card
    interaction.

-   **Get Card Serial Number**: Retrieve the serial
    number of the detected IsoDep card.

-   **Close Nfc Detection**: Terminate NFC detection when the operation
    is complete.

## **Who is this for?**

This documentation caters to developers of all levels who aim to
incorporate NFC card capabilities into their Ios native Whether
you\'re an experienced developer or just starting out, this library
provides a straightforward path to accomplish your objectives.

## Requirements

- iOS 13.0+
- Xcode 11.0+
- Swift 5.0+

## **Installation**
## **Integration with Xcode**

-   **Open Xcode**: Launch Xcode and open your Xcode project.
-   **Link Frameworks and Libraries**:

    -   In your Xcode project settings, navigate to the "General" tab.

    -   Scroll down to the "Frameworks, Libraries, and Embedded Content" section.

    -   Click the "+" button to add a new framework.

    -   Select the framework you added in the previous step from the list and click "Add".
      ![alt text](https://github.com/ahmedMohHegazy/sdkPdf/blob/main/1.jpeg)


-   **Import Framework**:

    -   In your source files where you want to use the framework, import it using `#import <FrameworkName/FrameworkName.h>`.

-   **Build and Run**: Build your project to ensure that the integration was successful.

### Adding Near Field Communication Tag Reading Capability

1. Open your project in Xcode.

2. Navigate to the project settings by clicking on the project name in the project navigator.

3. Select your app target under "Targets".

4. Go to the "Signing & Capabilities" tab.

5. Click the "+ Capability" button to add a new capability.

6. Search for "Near Field Communication Tag Reading" in the search bar and select it from the list.

7. Close the capability window.

8. Save your changes.

Now your app has the Near Field Communication Tag Reading capability enabled, allowing it to read NFC tags. Ensure that you have configured the necessary permissions and usage descriptions in your app's Info.plist file.


### Pod Info Editing

In order to enable NFC functionality in your iOS app, you need to make some edits to your project's Info.plist file.

1. Open your project's Info.plist file.

2. Add the following key-value pairs:

    ```xml
    <key>com.apple.developer.nfc.readersession.iso7816.select-identifiers</key>
    <array>
        <string>4D544A32303530333201</string>
    </array>
    ```

    This array contains the ISO 7816 select identifiers for your NFC tags. Make sure to replace these values with the appropriate identifiers for your specific use case.

3. Add the following key-value pair:

    ```xml
    <key>NFCReaderUsageDescription</key>
    <string>nfcTag</string>
    ```

    This key-value pair specifies the usage description for NFC reader in your app. Replace "nfcTag" with your desired description.

4. Save the changes to your Info.plist file.
### Entitlements File Editing

1. Open your project's entitlements file (`YourApp.entitlements`).

2. Add the following entitlement key:

    ```xml
    <key>com.apple.developer.nfc.readersession.formats</key>
    <array>
        <string>TAG</string>
    </array>
    ```


## **Available Functions**

-   **isAvailable():** Check if NFC is available on the device (returns
    Boolean: true/false).

-   **start(session: NFCTagReaderSession):** Begin listening for NFC tags.

-   **connectTag(tag: NFCTag, session: NFCTagReaderSession) async throws -> Bool:** Connect to an NFC tag (throws an error if connection fails).

-   **invalidate(errorMessage: String?):** Invalidate the current session (optionally with an error message).

-   **getSerailCard(tag: NFCISO7816Tag) async throws -> GeneralResponse:** Retrieve the serial number of an IsoDep card (returns a `GeneralResponse` object containing the serial number or error).

-   **readIsoDepCard(tag: NFCISO7816Tag) async throws -> NfcReadModel:** Read data from an IsoDep card (returns an `NfcReadModel` object containing read data or error).

-   **writeIsoDepCard(dataDecoded: String, tag: NFCISO7816Tag) async throws -> NfcReadModel:** Write data to an IsoDep card (throws an error if write fails, returns an `NfcReadModel` object containing response of write, card serial, and error).


## **Example Usage (IsoDepNfcManager - Swift)**


![alt text](https://github.com/ahmedMohHegazy/sdkPdf/blob/main/2.jpeg)
![alt text](https://github.com/ahmedMohHegazy/sdkPdf/blob/main/3.jpeg)
![alt text](https://github.com/ahmedMohHegazy/sdkPdf/blob/main/4.jpeg)
