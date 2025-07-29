Source: https://docs.fedoraproject.org/en-US/quick-docs/fonts/

---

## System Fonts

System fonts are installed for all users. Anyone with an account on the machine will be able to use these fonts.

Create a new directory in the system fonts directory (`/usr/local/share/fonts/`) to accommodate the new font family, and copy the downloaded fonts.

```shell
sudo mkdir -p /usr/local/share/fonts/<YOUR FONT>
sudo cp Downloads/<YOUR FONT>/* /usr/local/share/fonts/<YOUR FONT>
```

**NOTE:** Replace `<YOUR FONT>` with the actual name of the font.

<br>

## Set Permissions and Update SELinux Labels

```shell
sudo chown -R root: /usr/local/share/fonts/<YOUR FONT>
sudo chmod 644 /usr/local/share/fonts/<YOUR FONT>/*
sudo restorecon -vFr /usr/local/share/fonts/<YOUR FONT>
```

<br>

## Update the Font Cache

```shell
sudo fc-cache -v
```