FTP
===

**Table of Contents**

-   [Introduction](/intro/ftp.html)
-   [Installing/Configuring](/ftp/setup.html)
    -   [Requirements](/ftp/setup.html#Requirements)
    -   [Installation](/ftp/setup.html#Installation)
    -   [Runtime Configuration](/ftp/setup.html#Runtime%20Configuration)
    -   [Resource Types](/ftp/setup.html#Resource%20Types)
-   [Predefined Constants](/ftp/constants.html)
-   [Examples](/ftp/examples.html)
    -   [Basic usage](/ftp/examples.html#Basic%20usage)
-   [FTP Functions](/ref/ftp.html)
    -   [ftp\_alloc](/ref/ftp.html#ftp_alloc) — Allocates space for a
        file to be uploaded
    -   [ftp\_append](/ref/ftp.html#ftp_append) — Append the contents of
        a file to another file on the FTP server
    -   [ftp\_cdup](/ref/ftp.html#ftp_cdup) — Changes to the parent
        directory
    -   [ftp\_chdir](/ref/ftp.html#ftp_chdir) — Changes the current
        directory on a FTP server
    -   [ftp\_chmod](/ref/ftp.html#ftp_chmod) — Set permissions on a
        file via FTP
    -   [ftp\_close](/ref/ftp.html#ftp_close) — Closes an FTP connection
    -   [ftp\_connect](/ref/ftp.html#ftp_connect) — Opens an FTP
        connection
    -   [ftp\_delete](/ref/ftp.html#ftp_delete) — Deletes a file on the
        FTP server
    -   [ftp\_exec](/ref/ftp.html#ftp_exec) — Requests execution of a
        command on the FTP server
    -   [ftp\_fget](/ref/ftp.html#ftp_fget) — Downloads a file from the
        FTP server and saves to an open file
    -   [ftp\_fput](/ref/ftp.html#ftp_fput) — Uploads from an open file
        to the FTP server
    -   [ftp\_get\_option](/ref/ftp.html#ftp_get_option) — Retrieves
        various runtime behaviours of the current FTP stream
    -   [ftp\_get](/ref/ftp.html#ftp_get) — Downloads a file from the
        FTP server
    -   [ftp\_login](/ref/ftp.html#ftp_login) — Logs in to an FTP
        connection
    -   [ftp\_mdtm](/ref/ftp.html#ftp_mdtm) — Returns the last modified
        time of the given file
    -   [ftp\_mkdir](/ref/ftp.html#ftp_mkdir) — Creates a directory
    -   [ftp\_mlsd](/ref/ftp.html#ftp_mlsd) — Returns a list of files in
        the given directory
    -   [ftp\_nb\_continue](/ref/ftp.html#ftp_nb_continue) — Continues
        retrieving/sending a file (non-blocking)
    -   [ftp\_nb\_fget](/ref/ftp.html#ftp_nb_fget) — Retrieves a file
        from the FTP server and writes it to an open file (non-blocking)
    -   [ftp\_nb\_fput](/ref/ftp.html#ftp_nb_fput) — Stores a file from
        an open file to the FTP server (non-blocking)
    -   [ftp\_nb\_get](/ref/ftp.html#ftp_nb_get) — Retrieves a file from
        the FTP server and writes it to a local file (non-blocking)
    -   [ftp\_nb\_put](/ref/ftp.html#ftp_nb_put) — Stores a file on the
        FTP server (non-blocking)
    -   [ftp\_nlist](/ref/ftp.html#ftp_nlist) — Returns a list of files
        in the given directory
    -   [ftp\_pasv](/ref/ftp.html#ftp_pasv) — Turns passive mode on or
        off
    -   [ftp\_put](/ref/ftp.html#ftp_put) — Uploads a file to the FTP
        server
    -   [ftp\_pwd](/ref/ftp.html#ftp_pwd) — Returns the current
        directory name
    -   [ftp\_quit](/ref/ftp.html#ftp_quit) — Alias of ftp\_close
    -   [ftp\_raw](/ref/ftp.html#ftp_raw) — Sends an arbitrary command
        to an FTP server
    -   [ftp\_rawlist](/ref/ftp.html#ftp_rawlist) — Returns a detailed
        list of files in the given directory
    -   [ftp\_rename](/ref/ftp.html#ftp_rename) — Renames a file or a
        directory on the FTP server
    -   [ftp\_rmdir](/ref/ftp.html#ftp_rmdir) — Removes a directory
    -   [ftp\_set\_option](/ref/ftp.html#ftp_set_option) — Set
        miscellaneous runtime FTP options
    -   [ftp\_site](/ref/ftp.html#ftp_site) — Sends a SITE command to
        the server
    -   [ftp\_size](/ref/ftp.html#ftp_size) — Returns the size of the
        given file
    -   [ftp\_ssl\_connect](/ref/ftp.html#ftp_ssl_connect) — Opens a
        Secure SSL-FTP connection
    -   [ftp\_systype](/ref/ftp.html#ftp_systype) — Returns the system
        type identifier of the remote FTP server
