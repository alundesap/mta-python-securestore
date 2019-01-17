# mta-python-securestore
Multi-Target Application Python Example of interfacing with the Secure Store API

wget -c http://thedrop.sap-a-team.com/files/hana_ml-1.0.3.tar.gz ; wget -c http://thedrop.sap-a-team.com/files/XS_PYTHON00_1-70003433.ZIP ; mkdir -p sap_dependencies ; unzip XS_PYTHON00_1-70003433.ZIP -d sap_dependencies

cd python ; mkdir -p vendor ; pip download -d vendor -r requirements.txt --find-links ../sap_dependencies --find-links ../hana_ml-1.0.3.tar.gz ; cd ..

