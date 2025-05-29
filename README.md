# Secure and Dynamic Multi-Keyword Ranked Search Scheme over Encrypted Cloud Data

A comprehensive solution for secure and efficient searching over encrypted cloud data, enabling privacy-preserving data retrieval while maintaining data confidentiality.

## Overview

This project implements a secure search scheme that allows authorized users to perform efficient multi-keyword ranked searches over encrypted data stored in the cloud. The system ensures data privacy while maintaining search functionality and supporting dynamic updates to the encrypted dataset.

Check the explained video execution of the project - [video explanation](https://drive.google.com/file/d/1UCrVg9N4Bz3IZawNaFNetiNlGp3xTEv4/view?usp=sharing)

## Repository Links

- [Data Owner Component](https://github.com/s-prak/data_owner)
- [Data User Component](https://github.com/s-prak/data_user)
- [Encrypted Server Component](https://github.com/s-prak/encrypted-server)

## Quick Start Guide

### 1. Clone All Repositories

```bash
git clone https://github.com/s-prak/data_owner.git
git clone https://github.com/s-prak/data_user.git
git clone https://github.com/s-prak/encrypted-server.git
```

### 2. Start the Cloud Server (Encrypted Server)

```bash
cd encrypted-server
mvn clean install
mvn spring-boot:run
```

The server will run on `http://65.0.131.153:8081`

### 3. Start the Data Owner

```bash
cd data_owner
npm install
node file-upload-server.js  # Start the file upload server
node tfidf-server.js        # Start the TF-IDF server
cd app
npm start                   # Start the React frontend
```

The Data Owner interface will be available at `http://localhost:3000`

### 4. Start the Data User

```bash
cd data_user
npm install
npm start
```

The Data User interface will be available at `http://localhost:3001`

## Key Features

- **Secure Data Storage**: All data is encrypted before being stored in the cloud
- **Multi-Keyword Search**: Support for searching using multiple keywords
- **Ranked Results**: Search results are ranked based on relevance
- **Dynamic Updates**: Support for updating encrypted documents and indexes
- **Privacy-Preserving**: Cloud server cannot access plaintext data
- **Three-Tier Architecture**: Clear separation between Data Owner, Cloud Server, and Data User

## System Components

### 1. Data Owner

- Manages document collection
- Constructs and encrypts searchable index
- Handles document encryption
- Distributes necessary keys to authorized users
- Supports dynamic updates to the dataset

### 2. Cloud Server

- Stores encrypted documents and searchable index
- Performs search operations over encrypted data
- Returns top-ranked encrypted documents
- Handles updates to encrypted data
- Operates without access to plaintext data

### 3. Data User

- Authorized entity for performing searches
- Generates search trapdoors
- Decrypts retrieved documents
- Accesses required information securely

## Technology Stack

### Frontend

- React.js
- HTML5
- CSS3

### Backend

- Node.js
- Express.js
- MongoDB
- Java
- Spring Framework

### Tools

- Git
- Visual Studio Code
- GitHub

## Getting Started

### Prerequisites

- Node.js
- Java Development Kit (JDK)
- MongoDB
- Git

### Installation

1. Clone the repository:

```bash
git clone [repository-url]
```

2. Install dependencies for each component:

```bash
# For Data Owner
cd data-owner
npm install

# For Data User
cd data-user
npm install

# For Cloud Server
cd cloud-server
mvn install
```

3. Configure environment variables:

- Set up MongoDB connection strings
- Configure server ports
- Set up encryption keys

4. Start the services:

```bash
# Start Data Owner service
cd data-owner
npm start

# Start Data User service
cd data-user
npm start

# Start Cloud Server
cd cloud-server
mvn spring-boot:run
```

## Usage

1. Data Owner:

   - Access at: http://localhost:3000
   - Upload and encrypt documents
   - Manage access control

2. Cloud Server:

   - Access at: http://65.0.131.153:8081
   - Handles encrypted data storage and search

3. Data User:
   - Access at: http://localhost:3001
   - Perform secure searches
   - View and decrypt results

## Security Features

- End-to-end encryption
- Secure key distribution
- Privacy-preserving search
- Access control mechanisms
- Secure trapdoor generation
