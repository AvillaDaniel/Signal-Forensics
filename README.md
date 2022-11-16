
![pngaaa com-5782567 copy](https://user-images.githubusercontent.com/102838167/202283005-9b436713-5068-4a04-b573-0affd798f6d1.png)

# Signal-Forensics
Signal database acquisition and decryption.


![SQL](https://user-images.githubusercontent.com/102838167/202283462-514c167c-a3d7-447a-bede-50bc9322318c.PNG)

Unlike other applications, such as Whatsapp, Telegram, Messenger, etc., SIGNAL keeps its local database (signal.db) encrypted in AES-GCM mode, that is, even if it is possible to collect such a base through a collection physical (ROOT and others) or logical (DOWNGRADE), nothing can be done while it is not decrypted.
For this, we have to obtain three values ​​to decrypt the database, the first is the value of the key that is in the USERKEY_SignalSecret file, in HEXADECIMAL format, located in the KEYSTORE of the device. The other values ​​are present in the XML file, org.thoughtcrime.securesms_preferences.xml, located in Signal's root folder, being the CIFREADED TEXT with AUTHTAG (authentication TAG) + IV, all in BASE64 format.


## KEYSTORE SECRET KEY:
/data/misc/keystore/user_0/10123_USRSKEY_SignalSecret

## DATABASE: (Via Downgrade):
/data/user/0/org.thoughtcrime.securesms/databases/signal.db

## ENCRYPTED TEXT WITH AUTHTAG + IV: (Via Downgrade):
/data/user/0/org.thoughtcrime.securesms/shared_prefs/org.thoughtcrime.securesms_preferences.xml

KEYSTORE
“The Android Keystore system allows you to store cryptographic keys in a container to make it difficult to extract from the device. When the keys are in the Keystore, they can be used for cryptographic operations, and the material in them remains non-exportable. Furthermore, this feature provides facilities for restricting how and when the keys can be used, for example, requiring user authentication to use the keys or restricting the use of the keys only in certain cryptographic modes.”

https://developer.android.com/training/articles/keystore
![image](https://user-images.githubusercontent.com/102838167/202284214-2a813770-787f-4b41-a04a-53bb89cdde54.png)

