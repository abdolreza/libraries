CoinSpark libraries README - http://coinspark.org/


ABOUT
-----
The CoinSpark libraries help you integrate support for the CoinSpark protocol into
your wallet, or any other tool or service.

The libraries are available in 6 languages:

* C/C++
* Java
* Javascript
* PHP (5+)
* Python (2.5+)
* Ruby (1.9+)

The libraries for each language are functionally identical, and use as similar
calling conventions as possible, given the constraints imposed by each language. 

For more information and code examples: http://coinspark.org/developers/


HOW TO TEST
-----------
The libraries include extensive tests to verify that it behaves identically for
all inputs, for all languages. We encourage you to run these tests for yourself
by following the steps below. Explicit command line instructions are provided
for Unix-based systems.

* Download all the library files to your computer.

* In your Terminal, navigate to the directory containing those files

* Compile the C library tests:

gcc -o c/coinspark-test c/*.c -lm

* Run the executable:

c/coinspark-test

* Keep pressing return to accept all default options displayed.

* If no error is shown, the library has passed all internal C tests.

* Navigate to the directory containing the test files

cd CoinSpark-Tests-*

* For each '...-Input.txt' file, run the PHP test on that input:

php ../php/coinspark-test.php Address-Input.txt > Address-Output-PHP.txt
php ../php/coinspark-test.php AssetRef-Input.txt > AssetRef-Output-PHP.txt
php ../php/coinspark-test.php Script-Input.txt > Script-Output-PHP.txt
php ../php/coinspark-test.php AssetHash-Input.txt > AssetHash-Output-PHP.txt
php ../php/coinspark-test.php Genesis-Input.txt > Genesis-Output-PHP.txt
php ../php/coinspark-test.php Transfer-Input.txt > Transfer-Output-PHP.txt
php ../php/coinspark-test.php MessageHash-Input.txt > MessageHash-Output-PHP.txt

* Now check the corresponding PHP and C output files for differences

diff Address-Output-C.txt Address-Output-PHP.txt
diff AssetRef-Output-C.txt AssetRef-Output-PHP.txt
diff Script-Output-C.txt Script-Output-PHP.txt
diff AssetHash-Output-C.txt AssetHash-Output-PHP.txt
diff Genesis-Output-C.txt Genesis-Output-PHP.txt
diff Transfer-Output-C.txt Transfer-Output-PHP.txt
diff MessageHash-Output-C.txt MessageHash-Output-PHP.txt

* If no differences were reported, the library has passed the C-PHP consistency test.

* Feel free to look inside the input and output files to see what is going on.

* Python and Ruby tests run similarly to PHP. First, create Python and Ruby outputs:

python ../python/coinspark-test.py Address-Input.txt > Address-Output-Python.txt
python ../python/coinspark-test.py AssetRef-Input.txt > AssetRef-Output-Python.txt
python ../python/coinspark-test.py Script-Input.txt > Script-Output-Python.txt
python ../python/coinspark-test.py AssetHash-Input.txt > AssetHash-Output-Python.txt
python ../python/coinspark-test.py Genesis-Input.txt > Genesis-Output-Python.txt
python ../python/coinspark-test.py Transfer-Input.txt > Transfer-Output-Python.txt
python ../python/coinspark-test.py MessageHash-Input.txt > MessageHash-Output-Python.txt

ruby ../ruby/coinspark-test.rb Address-Input.txt > Address-Output-Ruby.txt
ruby ../ruby/coinspark-test.rb AssetRef-Input.txt > AssetRef-Output-Ruby.txt
ruby ../ruby/coinspark-test.rb Script-Input.txt > Script-Output-Ruby.txt
ruby ../ruby/coinspark-test.rb AssetHash-Input.txt > AssetHash-Output-Ruby.txt
ruby ../ruby/coinspark-test.rb Genesis-Input.txt > Genesis-Output-Ruby.txt
ruby ../ruby/coinspark-test.rb Transfer-Input.txt > Transfer-Output-Ruby.txt
ruby ../ruby/coinspark-test.rb MessageHash-Input.txt > MessageHash-Output-Ruby.txt

* Now check the corresponding Python/Ruby and C output files for differencess

diff Address-Output-C.txt Address-Output-Python.txt
diff AssetRef-Output-C.txt AssetRef-Output-Python.txt
diff Script-Output-C.txt Script-Output-Python.txt
diff AssetHash-Output-C.txt AssetHash-Output-Python.txt
diff Genesis-Output-C.txt Genesis-Output-Python.txt
diff Transfer-Output-C.txt Transfer-Output-Python.txt
diff MessageHash-Output-C.txt MessageHash-Output-Python.txt

diff Address-Output-C.txt Address-Output-Ruby.txt
diff AssetRef-Output-C.txt AssetRef-Output-Ruby.txt
diff Script-Output-C.txt Script-Output-Ruby.txt
diff AssetHash-Output-C.txt AssetHash-Output-Ruby.txt
diff Genesis-Output-C.txt Genesis-Output-Ruby.txt
diff Transfer-Output-C.txt Transfer-Output-Ruby.txt
diff MessageHash-Output-C.txt MessageHash-Output-Ruby.txt

* If no differences were reported, we've passed the C-Python and C-Ruby consistency tests.

* Java tests begin by compiling the Java classes:

javac ../java/src/main/java/org/coinspark/protocol/*.java

* Now run the CoinSparkTest class and keep pressing return to accept all the default options:

java -classpath ../java/src/main/java/ org.coinspark.protocol.CoinSparkTest

* Now check the corresponding Java and C output files for differencess

diff Address-Output-C.txt Address-Output-Java.txt
diff AssetRef-Output-C.txt AssetRef-Output-Java.txt
diff Script-Output-C.txt Script-Output-Java.txt
diff AssetHash-Output-C.txt AssetHash-Output-Java.txt
diff Genesis-Output-C.txt Genesis-Output-Java.txt
diff Transfer-Output-C.txt Transfer-Output-Java.txt
diff MessageHash-Output-C.txt MessageHash-Output-Java.txt

* If no differences were reported, the library has passed the C-Java consistency test.

* For the Javascript tests, you will need to open javascript/coinspark-test.html
in your web browser. Then for each '...-Input.txt' file generated by C, paste
the contents of that file into the left-hand field of the web page, then click
the arrow button at the top. Once Javascript has finished executing, the content
in the right-hand side of the page can be compared against the appropriate
'...-Output-C.txt' file, and should be identical.

* Cleaning up after the tests

cd ..
rm -r CoinSpark-Tests-*
rm c/coinspark-test
rm python/coinspark.pyc
rm java/src/main/java/org/coinspark/protocol/*.class



LICENSE (MIT)
-------------

Copyright (c) Coin Sciences Ltd

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.


CHANGELOG
---------

v2.1 - 10 February 2015
- Added complete Ruby (2.x) library
- Removed case insensitivity when checking binary hash matches in PHP, Python

v2.0.4 - 23 January 2015
- More efficient encoding for IPv4 message servers with no path

v2.0.3 - 14 January 2015
- Support bytearray for scripts in Python script<->metadata functions

v2.0.2 - 11 January 2015
* Added Python (2.x, 3.x) support for messaging

v2.0.1 - 7 January 2015
* Fixed byte length bug in transfers for a particular encoding variety

v2.0 - 6 January 2015
* Added support for CoinSpark messaging, Python to come

v1.0.4 - 24 November 2014
* Fixed typo in PHP's CoinSparkQueryAssetTrackingServer() function

v1.0.3 - 26 October 2014
* Added support for Python 3.x
* Added import required for paymentRef.randomize() on Python

v1.0.2 - 9 October 2014
* Added complete Python (2.x) library
* Seed random number generator in C test suite
* Fixed a return type typo in PHP and Javascript

v1.0.1 - 6 October 2014
* Removed RandomizeTransfer() in C test suite hard coded to default routes
* Fixed && -> & stylistic typo in PHP and Javascript libraries

v1.0 - 29 September 2014
* First release
