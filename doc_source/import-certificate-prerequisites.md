# Prerequisites for Importing Certificates<a name="import-certificate-prerequisites"></a>

To import a self–signed SSL/TLS certificate into ACM, you must provide the certificate and its private key\. To import a signed certificate, you must also include the certificate chain\. Your certificate must satisfy the following criteria:

+ The certificate must specify an algorithm and key size\. Currently, the following public key algorithms are supported by ACM: 

  + 1024\-bit RSA \(`RSA_1024`\)

  + 2048\-bit RSA \(`RSA_2048`\)

  + 4096\-bit RSA \(`RSA_4096`\)

  + Elliptic Prime Curve 256 bit \(`EC_prime256v1`\)

  + Elliptic Prime Curve 384 bit \(`EC_secp384r1`\)

  + Elliptic Prime Curve 521 bit \(`EC_secp521r1`\)

**Important**  
Note that [integrated services](http://docs.aws.amazon.com/acm/latest/userguide/acm-services.html) allow only algorithms and key sizes they support to be associated with their resources\. Further, their support differs depending on whether the certificate is imported into IAM or into ACM\. For more information, see the documentation for each service\.   
For Elastic Load Balancing, see [ HTTPS Listeners for Your Application Load Balancer](https://docs.aws.amazon.com/elasticloadbalancing/latest/application/create-https-listener.html)\.
For CloudFront, see [ Supported SSL/TLS Protocols and Ciphers](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/secure-connections-supported-viewer-protocols-ciphers.html#secure-connections-supported-ciphers)\.

+ The certificate must be an SSL/TLS X\.509 version 3 certificate\. It must contain a public key, the fully qualified domain name \(FQDN\) for your website, and information about the issuer\. The certificate can be self\-signed by your private key or by the private key of an issuing CA\. If your certificate is signed by a CA, you must include the certificate chain when you import your certificate\. 

+ The certificate must be valid at the time of import\. You cannot import a certificate before its validity period begins or after it expires\. The `NotBefore` certificate field contains the validity start date, and the `NotAfter` field contains the end date\.

+ The private key must be unencrypted\. You cannot import a private key that is protected by a password or passphrase\.

+ The certificate, private key, and certificate chain must be PEM–encoded\. For more information and examples, see [Certificate and Key Format for Importing](import-certificate-format.md)\.