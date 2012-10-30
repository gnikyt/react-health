# React Health

React Health is an fast and easy to use script to check the status (up/down) of a website.

## Fetch

The recommended way to install this script is [through composer](http://packagist.org).

Just create a composer.json file for your project:

```JSON
{
    "minimum-stability" : "dev",
    "require": {
        "tyler-king/react-health": "dev-master"
    }
}
```

And run these two commands to install it:

    $ curl -s http://getcomposer.org/installer | php
    $ php composer.phar install

## Usage

Execute the `react-health run` command.

```bash
$ vendor/bin/react-health run
```

By default it will use the `websites.json` file located in the react-health directory. To override with your website entries simply pass the the src argument as such:

```bash
$ vendor/bin/react-health run --src=/path/to/my/websites.json
```

Optionally you can also pass a list of websites or even run the command on a single website.

```bash
$ vendor/bin/react-health run --websites=github.com
$ vendor/bin/react-health run --websites=github.com,twitter.com
```

## Options

```bash
bin/react-health run --help
Usage:
 run [--src] [--websites]

Options:
 --src                 Location of website source file (json)
 --websites            Check a single or multiple websites (comma seperated).
 --help (-h)           Display this help message.
 --quiet (-q)          Do not output any message.
 --verbose (-v)        Increase verbosity of messages.
 --version (-V)        Display this application version.
 --ansi                Force ANSI output.
 --no-ansi             Disable ANSI output.
 --no-interaction (-n) Do not ask any interactive question.
```

## Example Output

```bash
bin/react-health run
+---------------------------------------+----------+
+ WEBSITE                               + STATUS   +
+---------------------------------------+----------+
+ this-will-fail-as-a-website.com       + DOWN 404 +
+---------------------------------------+----------+
+ reddit.com                            + UP 302   +
+---------------------------------------+----------+
+ facebook.com                          + UP 301   +
+---------------------------------------+----------+
+ github.com                            + UP 200   +
+---------------------------------------+----------+
+ twitter.com                           + UP 200   +
+---------------------------------------+----------+


Process time: 0.82 seconds.
There are 1 websites down. 4 websites up.
```