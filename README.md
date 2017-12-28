# Install OpenLDAP on MACOSX
Install Berkeley DB ```brew install berkeley-db```

Install OpenLDAP ```brew install openldap```

**Configuration**
  1. Open ```/etc/openldap/ldap.conf``` and configure Base and URI for ldap
  2. Open ```/etc/openldap/slapd.conf``` and configure ldap schemas, rootdn (this would be equivalent to root user id) and rootpw
  3. In order to generate rootpw, use command ```slappasswd -s your-password```

MV DB_Config ```mv /etc/openldap/DB_CONFIG.example /etc/openldap/DB_CONFIG```

Run OpenLDAP with command ```sudo /usr/libexec/slapd -d3```

Load various ldiff files via command ```ldapadd -D "cn=admin,dc=wso2,dc=com" -W -x -f <<filename>>```

To graphically view schema, download jxworkbench from http://jxplorer.org/

To query from commandline ```ldapsearch -D 'cn=admin,dc=ideasforsharing,dc=com' -W -x```
