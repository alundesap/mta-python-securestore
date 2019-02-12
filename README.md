# mta-python-securestore
Multi-Target Application Python Example of interfacing with the Secure Store API

# Description

This repo contains a complete example of interfacing with the SAP HANA Secure Store API.  It take the form of multi-target application(MTA) with the interfacing module written in the python programming language.

This example is referred to in the official SAP help documentation at the following link.

[Access the SAP HANA Secure Store with Python](https://help.sap.com/viewer/DRAFT/4505d0bdaf4948449b7f7379d24d0f0d/2.0.04/en-US/0d07ee1462c141beb8a86a92bc9cb92e.html)

# Requirements

The Secure Store functions are implmented in a SAP HANA Database instance and the sample application must be deployed to a space where the HANA instance is available.

This example project also requires python libraries provided by SAP to users with authorized access to download SAP software.

There is an current effort to make these libraries publically available.  See the To-Do section below.

Once installed or vendored, the following python libraries are provided to the python module of the application.

cfenv
sap_py_jwt
sap_xssec
hdbcli

# Download and Installation

wget -c http://thedrop.sap-a-team.com/files/hana_ml-1.0.3.tar.gz ; wget -c http://thedrop.sap-a-team.com/files/XS_PYTHON00_1-70003433.ZIP ; mkdir -p sap_dependencies ; unzip XS_PYTHON00_1-70003433.ZIP -d sap_dependencies


cd python ; mkdir -p vendor ; pip download -d vendor -r requirements.txt --find-links ../sap_dependencies --find-links ../hana_ml-1.0.3.tar.gz ; cd ..

mkdir -p target
mta --build-target CF --mtar target/python-securestore_cf.mtar build

cf deploy target/python-securestore_cf.mtar --use-namespaces

# Configuration

This example contains no configuration options.

# Limitations

This example is intended to illustrate the use of the Secure Storage API in a HANA system.  It does not contain extensive error handling or enforce a certain order of operations.  As such, certain assumptions apply and key values are hard coded.  For instance, you can not retrieve or delete a value before it's been created.

# Known Issues

This example contains no known issues and is provided "as-is".

# How to obtain support

This project is provided "as-is" with no expectation for major changes or support.

You may attemp

# Contributing

This project is provided "as-is" and is not accepting contributors.

# To-Do (upcoming changes)

The required python libraries may become publically available on PyPi at some point in the future.  If this becomes the case, the requirements will be simplified to remove the downloading of the SAP Python Libraries.

## License
 Copyright (c) 2017 SAP SE or an SAP affiliate company. All rights reserved.
 This file is licensed under the Apache Software License, v. 2 except as noted otherwise in the [LICENSE file](LICENSE).
