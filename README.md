# secureXchange

## About

This web page is a toolkit that enables the secure exchange of short messages. It includes tools for the generation of RSA encryption keys, as well as the encryption and decryption of messages using encryption keys. All functionality is embedded within this single file, including all HTML, CSS and JavaScript. To share this toolkit with others, simply share a copy of this single HTML file.

Messages are exchanged using 
[Public-key (asymmetric) cryptography](https://en.wikipedia.org/wiki/Public-key_cryptography)
and an 
[RSA encryption key-pair](https://en.wikipedia.org/wiki/RSA_(cryptosystem)). 
You may use your own RSA encryption key-pair or generate a new key-pair using the "Crypto Keys" tab on this page. The algorithm used to generate keys is a public-key encryption scheme combining the RSA algorithm with the Optimal Asymmetric Encryption Padding (OAEP) method. All cryptographic functions are performed using the 
[SubtleCrypto Web API standard](https://developer.mozilla.org/en-US/docs/Web/API/SubtleCrypto)
implemented by this browser. For this reason a modern browser must be used that 
[implements this API](https://caniuse.com/?search=SubtleCrypto), such as Chrome, Firefox, or Edge.

Please note that the maximum message length is determined by the key length and hash used to generate the original key-pair. Maximum message length is computed and displayed wherever key length and hash are set.

## Receiving Secure Messages

The following steps outline how to receive a secure message.

1. Enter a suitable RSA private encryption key in the PRIVATE KEY text area of the "Crypto Keys" tab. You may use an existing private key, or generate a new RSA encryption key-pair by pressing the "Generate RSA Keys" button on the tab. New keys will be generated and placed in the text areas for you. When generating new keys, please make sure to choose key length and hash parameters that permit the encryption of a message longer than the anticipated message.
2. Share your public key with the sender to be used to encrypt the message.
3. When the ciphertext message is received from the sender, enter it into the "Ciphertext Message" text area on the "Encrypt/Decrypt" tab and press the "Decrypt w/ Private Key" button. If the decryption succeeds, the decrypted message will appear in the "Plaintext Message" text area.

## Sending Secure Messages

The following steps outline how to send a secure message.

1. Obtain the receiver's RSA public key and paste it into the PUBLIC KEY text area on the "Crypto Keys" tab.
2. Enter then message to encrypt into the "Plaintext Message" text area of the "Encrypt/Decrypt" tab and press the "Encrypt w/ Public Key" button. If the encryption succeeds, the encrypted message will appear in the "Ciphertext Message" text area.
3. Copy the generated ciphertext and send it to the recipient. It is safe to send this message in the open because it only may be unencrypted using the corresponding RSA private encryption key.
