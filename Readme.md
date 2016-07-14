#jenkins
Custom Jenkins instance to do CI/CD builds

To update your plugins.txt
--------------------------

    export JENKINS_HOST=admin:password@jenkins-ci.rhel-cdk.10.1.2.2.xip.io
    curl -k -sSL "https://$JENKINS_HOST/pluginManager/api/xml?depth=1&xpath=/*/*/shortName|/*/*/version&wrapper=plugins" | perl -pe 's/.*?<shortName>([\w-]+).*?<version>([^<]+)()(<\/\w+>)+/\1 \2\n/g'|sed 's/ /:/' > plugins.txt



