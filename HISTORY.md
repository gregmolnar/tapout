# RELEASE HISTORY

## 0.4.3 / 2013-11-18

New feature allows producers to emit a *pause document* and 
*resume document* code to halt and resume test result processing.
While processing is halted, $stdin is directed back to $stdout
uninterpreted.

Changes:

* Add support for pause and resume code.


## 0.4.2 / 2013-03-18

This release adds support for trace depth and snippet size options.

Changes:

* Tie trace depth config into backtrace filter.
* Tie lines config into snippet creator.


## 0.4.1 / 2012-04-16

Add support for autoloading reporter plugins. Just name the plugin script
the same as the reporter prefixed by `tapout-`, e.g. `tapout-fivemat.rb`.

Changes:

* Add support for autoloading reporter plugins.
* Add -r/-require option to tapout command.


## 0.4.0 / 2012-02-01

TAP-Y/J spec now supports `stdout` and `stderr` fields. This allows test
frameworks to capture stdout and stderr while running tests and pipe them
through with the TAP stream, which tapout can then include in the test
report output. This release also brings a great deal of improvement to test
reports in general, from better time stats to much improved backtrace output.

Changes:

* Rename namespace to Tapout, instead of TapOut.
* Add support for `stdout` and `stderr` fields to spec.
* Add common config for all reporters.
* Add common code snippet functionality to all reporters.
* Add markdown reporter.


## 0.3.2 / 2011-11-08

Improve backtrace output in a number of reporters. Now, by default, full
backtraces are provided. Use the `--trace DEPTH` option to limit the
number of backtrace lines to report.

Changes:

* Improve backtrace output in most reporters.


## 0.3.1 / 2011-10-18

This release fixes an error raised when no report format is explicitly specified.
Where as it is supposed to default to the `dot` reporter. It also adds initial
support for error/failure `class` field.

Changes:

* Fix default reporter issue. (Brad Murray) #1
* Add support for class field to Turn reporter.


## 0.3.0 / 2011-10-09

This release supports revision 3 of the TAP-Y/J specification, which adds `final`
to the document types. The `final` document is the last document of a test suite.
It takes the place of `tally`, which is now simply an optional running subtotal
document. 

This release also makes some interface improvements to the `Reporters::Abstract`
base class and ports over all applicable reporters from the Turn project.

Changes:

* Use `final` instead of `tally` for last entry.
* Port Turn report formats.


## 0.2.3 / 2011-10-08

Exit code are important for a test output format. This release addressed that
issue.

Changes:

* Fixed exit code.


## 0.2.2 / 2011-10-07

Fixed incorrect tally entry in breakdown reporter.

Changes:

* Fixed incorrect tally entry in breakdown reporter.
* Add integration specs for reporters.


## 0.2.1 / 2011-10-06

A quick fix for a malformed require call in the HTML reporter,
and a fix for indention in the legacy TAP adapter.

Changes:

* Fix require in html reporter.
* Fix indention of YAML in legacy TAP adapter.


## 0.2.0 / 2011-10-06

This release revises the specification a bit, primarily
changing the names of header and footer sections to more
semantically useful terms, suite and tally, respectively.
Also, a `rev` field has been added to the suite entries
to allow consuming apps to gracefully handle any future
changes.

Changes:

* Rename header and footer to suite and tally.
* Add rev field to suite entry.


## 0.1.0 / 2011-05-21

This is the first public release of TapOut, a TAP and TAP-Y/J output
formatter.

Changes:

* Happy Release Day!

