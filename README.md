# Tipax

The first implemented use case imports the Tipax city/state catalog into `tblTipaxAdress`.

`POST /api/tipax/cities/import` checks whether the table already contains any row. If so, it does nothing. Otherwise it obtains a Tipax bearer token, calls `GET /api/OM/v3/Cities/plusstate`, removes duplicate Tipax city IDs and inserts the result.

Runtime secrets belong in user-secrets or environment-specific configuration; do not commit them to `appsettings.json`.
