# pass21password

This repository is a fork of [reinefjord/pass2csv](https://github.com/reinefjord/pass2csv).
The script will not adhere to `KPX_FORMAT`, instead it will attempt to generate a 1password-compatible CSV file.

This script is tailored to **my** needs and will probably need adjusting before used for your specific directory structure.

---

Needs [python-gnupg](https://pypi.python.org/pypi/python-gnupg) and python3.
Run with path to password store as argument:

```
python3 -m pip install --user python-gnupg
python3 pass2csv.py ~/.password-store
```

There are two ways to export CSV data:

1.  The format for [1Password](https://support.1password.com/create-csv-files/):

        title,website,username,password,notes,*custom_fields

    Where 'Password' is the first line of the entry in `pass` and 'Notes' are all
    subsequent lines.
