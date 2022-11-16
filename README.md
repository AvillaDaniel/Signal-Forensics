
![pngaaa com-5782567 rrrrcopy](https://user-images.githubusercontent.com/102838167/202285981-e2a0413e-a6b6-4cd0-8952-adbbf66ba7d7.png)

# Signal-Forensics
Signal database acquisition and decryption.

![signal](https://user-images.githubusercontent.com/102838167/202285009-4fdb283b-466c-47ae-9d8f-532d30d52cff.PNG)

Unlike other applications, such as Whatsapp, Telegram, Messenger, etc., SIGNAL keeps its local database (signal.db) encrypted in AES-GCM mode, that is, even if it is possible to collect such a base through a collection physical (ROOT and others) or logical (DOWNGRADE), nothing can be done while it is not decrypted.
For this, we have to obtain three values ​​to decrypt the database, the first is the value of the key that is in the USERKEY_SignalSecret file, in HEXADECIMAL format, located in the KEYSTORE of the device. The other values ​​are present in the XML file, org.thoughtcrime.securesms_preferences.xml, located in Signal's root folder, being the CIFREADED TEXT with AUTHTAG (authentication TAG) + IV, all in BASE64 format.

## KEYSTORE SECRET KEY:
/data/misc/keystore/user_0/10123_USRSKEY_SignalSecret

## DATABASE: (Via Downgrade):
/data/user/0/org.thoughtcrime.securesms/databases/signal.db

## ENCRYPTED TEXT WITH AUTHTAG + IV: (Via Downgrade):
/data/user/0/org.thoughtcrime.securesms/shared_prefs/org.thoughtcrime.securesms_preferences.xml

## KEYSTORE
“The Android Keystore system allows you to store cryptographic keys in a container to make it difficult to extract from the device. When the keys are in the Keystore, they can be used for cryptographic operations, and the material in them remains non-exportable. Furthermore, this feature provides facilities for restricting how and when the keys can be used, for example, requiring user authentication to use the keys or restricting the use of the keys only in certain cryptographic modes.”

https://developer.android.com/training/articles/keystore

![SQL](https://user-images.githubusercontent.com/102838167/202283462-514c167c-a3d7-447a-bede-50bc9322318c.PNG)

![2022-02-09 (47)](https://user-images.githubusercontent.com/102838167/202285590-2faf5171-4dc4-40b3-8fa8-e0df7cf4af68.png)

![2022-02-09 (39)](https://user-images.githubusercontent.com/102838167/202285490-1150c302-58ff-4bcb-98bf-0560c5e1cf8a.png)

![2022-02-09 (38)](https://user-images.githubusercontent.com/102838167/202285394-04e444f5-64f1-46c9-8947-c24ad9783dfa.png)

