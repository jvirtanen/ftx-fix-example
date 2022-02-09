# FTX FIX Example

This is a simple example application that demonstrates how to connect to
[FTX][] using the [FIX API][] and [Philadelphia][], an open source
FIX engine for the JVM.

  [FTX]: https://ftx.com
  [FIX API]: https://docs.ftx.com/#fix-api
  [Philadelphia]: https://github.com/paritytrading/philadelphia

Building and running this application requires Java Development Kit (JDK) 11
or newer and Maven.

## Usage

To build and run the application, follow these steps:

1. Install [stunnel][], for example, using [Homebrew][]:

    ```shell
    brew install stunnel
    ```

2. Download the TLS certificate:

    ```shell
    openssl s_client -showcerts -connect fix.ftx.com:4363 < /dev/null | \
        openssl x509 -outform PEM > fix.ftx.com.pem
    ```

3. Build the application:

    ```shell
    mvn package
    ```

4. Create a configuration file, `etc/example.conf`:

    ```shell
    cp etc/example.conf.template etc/example.conf
    ```

5. Fill in the API key and API secret in the configuration file,
   `etc/example.conf`.

6. Start stunnel:

    ```shell
    stunnel etc/stunnel.conf
    ```

7. Run the application:

    ```shell
    java -jar ftx-fix-example.jar etc/example.conf
    ```

The application logs onto FTX and immediately logs out.

  [stunnel]: https://www.stunnel.org
  [Homebrew]: https://brew.sh

## License

Copyright 2022 Jussi Virtanen.

Released under the Apache License, Version 2.0. See `LICENSE.txt` for details.
