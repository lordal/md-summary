A tool for summarizing SAML federation metadata. It tries to
identify the software running on each IdP and SP using the endpoint
URLs and entityIDs.
It can filter on registration authority, entity categories and assurance certification.

### Requirements

* perl 5.18 or newer
* XML::LibXML

### Usage

    md-summary -f metadata.xml [-h|--help] [-a] [-e] [-r] [-l] [ -s <regAuth>] [-t <ent cat>] [-u <assurance>]

      -h | --help    Prints this help message.

      -a             Prints assurance-certification.
      -e             Prints entity category stats.
      -r             Prints registration authority stats.
      -l             Lists entities for the above.

      -f <md file>   File to parse.

      -s <reg auth>  Show only entities registered with specific federation.
      -t <ent cat>   Show only entities with specific entity category.
      -u <assurance> Show only entities with specific assurance.


### Example

    % curl -s -o edugain.xml http://mds.edugain.org
    % ./md-summary -f edugain.xml -r
    Identity Providers (2092):
      Shibboleth                       1680 ( 80.3%)
      SimpleSAMLphp                     145 (  6.9%)
      OpenAthens                        122 (  5.8%)
      ADFS                               96 (  4.6%)
      SURFconext ADFS?                   19 (  0.9%)
      Other                              11 (  0.5%)
      PingFederate                        7 (  0.3%)
      Authentic 2                         5 (  0.2%)
      IBM Tivoli FIM                      3 (  0.1%)
      Novell Access Manager               2 (  0.1%)
      PySAML                              1 (  0.0%)
      CA SiteMinder                       1 (  0.0%)

    Per federation
      http://ukfederation.org.uk        657 ( 31.4%)
      https://incommon.org              405 ( 19.4%)
      https://federation.renater.fr/    261 ( 12.5%)
      http://cafe.rnp.br                140 (  6.7%)
      http://www.surfconext.nl/          85 (  4.1%)
      http://www.idem.garr.it/           72 (  3.4%)
      http://www.eduid.cz/               63 (  3.0%)
      https://www.wayf.dk                59 (  2.8%)
      http://www.swamid.se/              47 (  2.2%)
      https://www.aai.dfn.de             45 (  2.2%)
      [snip]


    Service Providers (1209):
      Shibboleth                       1014 ( 83.9%)
      SimpleSAMLphp                      75 (  6.2%)
      Other                              72 (  6.0%)
      ADFS                               16 (  1.3%)
      RSmart OneCampus?                   7 (  0.6%)
      PingFederate                        6 (  0.5%)
      iModules?                           6 (  0.5%)
      ExLibris?                           4 (  0.3%)
      PySAML                              3 (  0.2%)
      Kaltura?                            2 (  0.2%)
      UprisingTech?                       1 (  0.1%)
      Cornerstone                         1 (  0.1%)
      Kuali                               1 (  0.1%)
      Instructure?                        1 (  0.1%)

    Per federation
      http://ukfederation.org.uk        836 ( 69.1%)
      https://incommon.org              114 (  9.4%)
      https://www.aai.dfn.de             51 (  4.2%)
      http://www.idem.garr.it/           34 (  2.8%)
      https://federation.renater.fr/     32 (  2.6%)
      http://www.swamid.se/              27 (  2.2%)
      http://www.eduid.cz/               13 (  1.1%)
      http://rr.aai.switch.ch/           12 (  1.0%)
      http://aai.grnet.gr/               11 (  0.9%)
      http://www.csc.fi/haka             11 (  0.9%)
      [snip]


    %
    % ./md-summary -f edugain.xml -s 'http://www.swamid.se/' -e
    Shows stats for SWAMID with entity category information

### Bugs, Issues, etc.

Yes, probably.
