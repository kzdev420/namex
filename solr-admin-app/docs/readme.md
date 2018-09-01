
#### SSO Admin Setup:

Create client "namex-solr-admin-app" with a Client Protocol of `openid-connect` and Access Type `confidential`. Add
Valid Redirect URI `http://localhost:8080/oidc_callback` for doing desktop development.

#### Defects
1. Export of synonym_audit loses date and time information
1. Edit page should use a text area for large varchar strings
1. Inline edit box for synonyms needs to be larger
1. Inline editing of synonyms alphabetizes but is not displayed properly
1. Determine why menu items are sometimes missing on first load
1. Can't inline edit booleans (github.com/flask-admin/flask-admin/issues/1604)
1. If you're on page 2 when less than 1000 items, switching to 1000 per page fails

#### Deficiencies - Application
1. Make the audit tables filterable on Action column
1. Push data from test to dev and prod
1. Flag to make data readonly in dev and prod
1. After data has been completed make the Category non-null 
1. SSO authorization based on group
1. Display username and add logout button
1. Add DB-based Stop Words to Solr
1. Determine if there is a way to highlight search matches

#### Deficiencies - Code
1. Add version numbers to requirements.txt
1. Globals: explore use of `__all__`
1. Do docstrings
1. Determine if bootstrap files, etc, should be in repo
1. Document the local development setup.
1. Determine if the Keycloak singleton is pythonic enough
1. Fix the warning for the dotenv import in config.py
1. Sort out what the Flask SECRET_KEY is used for
1. Move templates to better place / do jinja properly
1. Fix desktop to run on port 8080, not 5000
1. Determine if Alembic should be used for migrating database changes
1. Use gunicorn or something else to get rid of WSGI warning
1. Make the audit action an enum in the model
1. Implement test suite
1. Move the solr core names to somewhere easily configurable
1. Add error reporting for Solr core reloading
1. Don't reload solr cores if only the category or comment change

#### Deficiencies - OpenShift
1. Make route not visible from internet, much like solr is done
1. NAMEX-API builds on commit of this app
1. Automate build of image for latest
1. Magic stuff for PostgreSQL volumes
1. Turn off debug in openshift
1. Handle changes to postgres credentials