# pass21password

This repository is a fork of [reinefjord/pass2csv](https://github.com/reinefjord/pass2csv).
The script will not adhere to `KPX_FORMAT`, instead it will attempt to generate a 1password-compatible CSV file.

This script is tailored to **my** needs and will probably need adjusting before used for your specific directory structure.

It asserts the following structure inside the pass store:

        example.com/foobar.gpg

- All passwords are inside a directory (the directory name is stored as the `name` & `url` field!
- The file name is the username (e.g. `foobar` is the username for `example.com`, so the path is `example.com/foobar.gpg`)
- The first line of the gpg file is the password (e.g. `foobar.gpg` contains `example123` when decrypted)
- All other lines are stored in the `notes` field of the resulting csv

---

Needs [python-gnupg](https://pypi.python.org/pypi/python-gnupg) and python3.
Run with path to password store as argument:

```
python3 -m pip install --user python-gnupg
python3 pass2csv.py ~/.password-store
```

The format for [1Password](https://support.1password.com/create-csv-files/):

        title,website,username,password,notes,*custom_fields

Where 'Password' is the first line of the entry in `pass` and 'Notes' are all subsequent lines.
