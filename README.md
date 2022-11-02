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

1. Build the application:

    ```shell
    mvn package
    ```

2. Create a configuration file, `etc/example.conf`:

    ```shell
    cp etc/example.conf.template etc/example.conf
    ```

3. Fill in the API key and API secret in the configuration file,
   `etc/example.conf`.

4. Run the application:

    ```shell
    java -jar ftx-fix-example.jar etc/example.conf
    ```

The application logs onto FTX and immediately logs out.

## License

Copyright 2022 Jussi Virtanen.

Released under the Apache License, Version 2.0. See `LICENSE.txt` for details.
