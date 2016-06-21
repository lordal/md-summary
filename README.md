A simple tool for summarizing SAML federation metadata. It tries to
identify the software running on each IdP and SP using the endpoint
URLs and entityIDs.

### Requirements

* perl 5.18 or newer
* XML::LibXML

### Usage

    md-summary -f metadata.xml [-h] [-e] [-r] [ -s <regAuth>]

    -h | --help   Prints this help message.
    -e            Prints entity category stats.
    -r            Prints registration authority stats.
    -f <md file>  File to parse.
    -s <reg auth> Show only entites registered with specific
                  federation.


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
      http://aai.grnet.gr/               35 (  1.7%)
      http://rr.aai.switch.ch/           34 (  1.6%)
      http://www.heanet.ie               29 (  1.4%)
      http://federation.belnet.be/       18 (  0.9%)
      http://www.canarie.ca              18 (  0.9%)
      http://eduid.at                    17 (  0.8%)
      http://aai.arnes.si                14 (  0.7%)
      http://laife.lanet.lv/             14 (  0.7%)
      http://www.rediris.es/             14 (  0.7%)
      http://www.csc.fi/haka             12 (  0.6%)
      http://eduid.hu                    12 (  0.6%)
      https://aai.pionier.net.pl         10 (  0.5%)
      http://taat.edu.ee                  4 (  0.2%)
      https://fedi.litnet.lt              4 (  0.2%)
      http://eduid.lu                     4 (  0.2%)
      https://www.fccn.pt                 2 (  0.1%)
      https://www.gakunin.jp              2 (  0.1%)
      https://mtd.gif.grena.ge            2 (  0.1%)
      https://peano.uran.ua               2 (  0.1%)
      http://federations.renam.md/        2 (  0.1%)
      http://cofre.reuna.cl               2 (  0.1%)
      http://colfire.co                   1 (  0.0%)
      https://aaf.edu.au                  1 (  0.0%)
      http://iif.iucc.ac.il               1 (  0.0%)
      https://aai.asnet.am                1 (  0.0%)
      https://minga.cedia.org.ec          1 (  0.0%)
      http://www.srce.hr                  1 (  0.0%)
      http://feide.no/                    1 (  0.0%)



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
      http://eduid.hu                    10 (  0.8%)
      http://www.surfconext.nl/           7 (  0.6%)
      http://feide.no/                    6 (  0.5%)
      http://cofre.reuna.cl               6 (  0.5%)
      http://www.heanet.ie                5 (  0.4%)
      https://www.wayf.dk                 5 (  0.4%)
      http://eduid.at                     4 (  0.3%)
      http://aai.arnes.si                 4 (  0.3%)
      https://aai.asnet.am                3 (  0.2%)
      http://eduid.lu                     3 (  0.2%)
      https://peano.uran.ua               3 (  0.2%)
      http://www.srce.hr                  2 (  0.2%)
      http://www.rediris.es/              2 (  0.2%)
      https://www.gakunin.jp              2 (  0.2%)
      http://www.canarie.ca               2 (  0.2%)
      http://iif.iucc.ac.il               1 (  0.1%)
      https://www.fccn.pt                 1 (  0.1%)
      https://aai.pionier.net.pl          1 (  0.1%)
      http://federations.renam.md/        1 (  0.1%)
    %

### Bugs, Issues, etc.

Yes, probably.
