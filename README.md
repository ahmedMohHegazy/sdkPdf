# **Androiod NfcManager Library Documentation**

Welcome to the comprehensive documentation for utilizing the NfcManager
library, facilitating the reading and writing operations for
IsoDep,MifareClassic NFC cards. This library streamlines the process for
developers working on Android native or React Native applications,
enabling convenient integration of NFC card functionality.

## **Key Features**

-   **Read and Write**: Seamlessly read from and write to
    IsoDep,MifareClassic NFC cards.

-   **Start Nfc Detection**: Initiate NFC detection for card
    interaction.

-   **Get Card Serial Number (for IsoDep Cards)**: Retrieve the serial
    number of the detected IsoDep card.

-   **Close Nfc Detection**: Terminate NFC detection when the operation
    is complete.

## **Who is this for?**

This documentation caters to developers of all levels who aim to
incorporate NFC card capabilities into their Android native Whether
you\'re an experienced developer or just starting out, this library
provides a straightforward path to accomplish your objectives.

## **Installation**

-   **Open Android Studio**: Launch Android Studio and open your
    existing project.

-   **Access Project Structure**: Navigate to File \> Project Structure.

-   **Manage Dependencies**: Proceed to the Dependencies tab.

-   **Add Dependency**:

    -   Click the \"Add\" button and select \"JAR/AAR dependency\".

    -   Locate the downloaded JAR/AAR file for your library (e.g.,
        NfcManager.aar) in the \"File Selection\" dialog, and paste the
        full path into the field.

-   **Add and Sync Gradle**: Click \"OK\" to add the dependency. Android
    Studio will automatically trigger a Gradle sync to update your
    project configuration.

**Usage**

Import the necessary module at the top of your file:

![alt text](https://github.com/ahmedMohHegazy/sdkPdf/blob/main/e4112785ca1ca1682cf455a2f6fa19d7a4af1bf0.png)

Initialize the NfcManager:

![alt text](https://github.com/ahmedMohHegazy/sdkPdf/blob/main/47aa5a84502968ccc831b8936f60f4d92b3a5769.png)

In the **onCreate** function:

![alt text](https://github.com/ahmedMohHegazy/sdkPdf/blob/main/648e358db161e346f30d292842cd8085322dd991.png)

## **Available Functions**

-   **isEnabled():** Check if NFC is enabled on the device (returns
    Boolean: true/false).

-   **start():** Begin listening for NFC tags.

-   **registerTagEvent():** Register for NFC tag events.

-   **requestTechnology(tags: ArrayList\<String\>):** Request NFC
    technologies (accepts an array of NFC tag types).

-   **getSerialCard(tag: Tag, tech: String):** Retrieve the serial
    number of an IsoDep card (returns a String).

-   **readIsoDepCard(tag: Tag, tech: String):** Read data from an IsoDep
    card (returns an object containing read data, card serial, and
    isError).

-   **writeIsoDepCard(tag: Tag, tech: String, bytes: ByteArray):** Write
    data to an IsoDep card (returns an object containing response of
    write \*should return 144 if everything go correctly , card serial,
    and isError).

-   **readMifareClassicCard(tag: Tag, pwd: ArrayList\<Byte\>):** Read
    data from a Mifare Classic card (requires authentication with a
    password, returns an object containing read data and isError).

-   **writeMifareClassicCard(tag: Tag, pwd: ArrayList\<Byte\>, bytes:
    ByteArray):** Write data to a Mifare Classic card (requires
    authentication with a password, returns an object containing
    response of write \*should return success if everything go
    correctly\* and isError).

-   **close():** Unregister NFC detection when operations are complete.

## **Example Usage (IsoDepNfcManager - Kotlin)**

![alt text](https://github.com/ahmedMohHegazy/sdkPdf/blob/main/ae85872fb8405df4ead75d384af11dc5d34b8f9f.png)

![alt text](https://github.com/ahmedMohHegazy/sdkPdf/blob/main/2ae1ec3f88b32b146dd01cd61d87489e62fbebd4.png)

## **Example Usage (MifareClassicNfcManager - Kotlin)**

![alt text](https://github.com/ahmedMohHegazy/sdkPdf/blob/main/f56cef32392641142360fc9e69012b85d80f5f45.png)

![alt text](https://github.com/ahmedMohHegazy/sdkPdf/blob/main/image4.png)
