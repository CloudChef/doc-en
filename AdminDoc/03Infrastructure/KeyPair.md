**Key Pair**


Key pair is the login credentials of the process of the user accessing the created virtual machine, installing the agent, and so on. The infrastructure administrator, tenant administrator, and sysadmin can manage key pairs through the key pair interface, including create, import, download, and delete.

The infrastructure administrator and tenant administrator can only see the key pair they created and imported, and sysadmin can see all the key pairs under the tenant.

# Create a New Key

Infrastructure administrators, tenant administrators, and sysadmin can create new keys.

In the left navigation bar, select "Infrastructure" - "Key Pair" and click "New Key". Enter the key name (can only be numbers or letters), the selection algorithm (RSA), and the length. Currently, key generations of three lengths of 1024, 2048, and 4096 are supported. Click "Submit" and you will see the generated key pair on the key pair list interface.

# Import a Key

The private and public keys can be imported and saved in the system for subsequent use (for example, the corresponding public key has been configured in the virtual machine image). Click "Import Key", enter the key name, fill in the private key or / and public key, and click "Import". When importing, the private key or public key must be filled in. After the import is successful, the imported key will be seen in the list interface.

# Download the private key

If the public key has a private key (new key has both public and private keys), select a key pair in the list, the "Download Private Key" button will become available, click Download to download the private key corresponding to the public key. 

# Use a Key Pair

In the OpenStack VM template, if you select the authentication type of the key pair, you will select the existing key pair (created or imported) in the system. Here, you can only select the public key, and the private key will be filtered.
