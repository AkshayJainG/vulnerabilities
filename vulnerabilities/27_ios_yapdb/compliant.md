
It is suggested to use custom encryption while storing data in Yap
databases.

SQLCipher is a SQLite extension that transparently encrypts the entire
database, and is available under a BSD-style license. SQLCipher support
has been added as a Cocoapod subspec. Simply change your Podfile:

    pod 'YapDatabase/SQLCipher'

If you aren't using the SQLCipher subspec, the project won't compile the
encryption configuration options to prevent the case of accidentally
trying to use encryption when support is not available.

Once the project is configured to use SQLCipher, it then needs to tell
YapDatabase the passphrase. This is done by setting the cipherKeyBlock
of YapDatabaseOptions.

    YapDatabaseOptions *options = [[YapDatabaseOptions alloc] init];
        options.corruptAction = YapDatabaseCorruptAction_Fail;
        options.cipherKeyBlock = ^ NSData *(void){
            // You can also do things like fetch from the keychain in here.
            return [@"super secure passphrase" dataUsingEncoding:NSUTF8StringEncoding];

            // Note: The return type is NSData, and does NOT have to be a string in UTF-8.
            // It can be any kind of blob of data, including randomly generated bytes.
        };

        self.database = [[YapDatabase alloc] initWithPath:databasePath options:options];

The cipherKeyBlock helps prevent storing the credentials in memory any
longer than necessary. This block will be executed on database setup,
and when new connections are made to the database.
