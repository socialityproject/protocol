# The Sociality Project Protocol
This Document is (c) 2015 The Sociality Project, Inc.

## LICENSE

## Table of Contents
1. License
2. Table of Contents
3. Purpose
4. Protocol
  0. Overview
  1. Encryption
  2. Networks Vs. Self-Hosting
  3. Key Servers
  4. User Profile
  5. Sharing Data
  6. Commenting
  7. Messaging
  8. Revoking Access
5. Requirements for SaaSS
6. Additional Details

## Purpose
### Organization Purpose
The Sociality Project is an Open Source Organization whose sole purpose is the creation and advancement of 
Advertising-Free Social Networks, that value user individualism and privacy over profit. This document is 
step one for detailing what we expect to accomplish.

### Protocol Purpose
The protocol for The Sociality Project, dubbed Sociality Protocol, is technology agnostic, and this document must 
remain clear of anything overly technical, with the exception of explaining base requirements for encryption 
standards.

### Current Version
Current Version of this protocol document: 0.1-20150918

## Protocol
### Overview
The Sociality Protocol is a set of loosely coupled concepts that enable users to manage profiles, share data, 
and comment.

#### Implementing the Protocol
The idea behind The Sociality Protocol is to have a mesh network of user's personal servers, or larger community-based network servers, that can interact with each other, without the requirement for a particular software. The Sociality Project will provide developers with prototypes that helps explain the protocol, but the prototype should not be used by normal end-users who want a complete experience.

##### Standards
Since the network should be comprised of servers, and key servers, there is an expected standard to uphold when communicating with each other.
1. All software must embrace a simple RESTful interface for data exchanges.
2. All software must embrace encryption of everything with a user.
3. All software must adhere to a simple data format when exporting and importing user's content.
4. All software must embrace open source.

### Encryption
#### Public Key Encryption
Every bit of content, must be encrypted with a public key, similar to PGP/GPG. Allowing the sharing of the public key enables user-to-user communication, where the key is the only way to unlock the content from a single user. Keys can be revoked by a user due to "unfriending" or in the event of a compromise (See Revoking Access).
Keeping user content secure is the main purpose for using Public Key Encryption, so the protocol suggests a very strong, greater than 2048 bytes of entropy for the public key, but 2048 bytes should be the standard.

#### Secure Socket Layer
If a private network is accessible via the internet, it must use SSL enabled by default. An SSL certificate that is self-signed may be allowed, but it is preferred that a trusted certificate be used. In the instance of a network, an Extended Validation SSL Certificate must be used.

### Networks Vs. Self-Hosting
The purpose of this protocol is to allow data interchange between different users who have certain preferences. This section will help define the expected preferences for those users.

#### Network
A Network using The Sociality Protocol is an entity that is hosting multiple user profiles on a single domain. This is similar to current social networks like Facebook, Twitter, Instagram, etc. It should be common for a Network to exist using The Sociality Protocol, as long as they adhere to the primary rules of the protocol. A Network should allow data interchange between users who are not on the Network, but have a profile on a trusted key server. Networks may choose to use their own key server, but they must also allow users to specify a different key server to exchange with.

#### Self-Hosted
A user may decide to self-host their own software on a server of their choosing, including locally on a user's machine.

### Key Servers
Trusted key servers may be run by third-parties, as well mail providers, and anyone may setup their own key server for exchanging keys. Profiles may use either a username or email address to identify the user. In the case of an anonymous community, a hash of the primary IP address may be used in lieu of a username or email address.

Key servers must allow for exchange between users, either through an RESTful interface, or through e-mail. All public keys that reside on a key server database must also encrypt the key string with the user's password as the key, in the chance of a database compromise.

#### Exchanging Keys
The process for exchanging keys is as follows:
1. Primary User searches key server for username or email address or IP address hash of Other User to add.
2. Key Server notifies Other User that the Primary User wants to share data, and passes on the Primary User's key for storage.
3. If Other User accepts, the key server notifies Primary User with the Other User's key.

The Key Server must also indicate the type of content the Primary User wants to access. (see Sharing Data)

### User Profile
A user profile consists of the following items:
1. Username/E-mail Address/IP Address Hash

### Sharing Data
### Commenting
### Revoking Access

## Requirements for SaaSS
## Additional Details
