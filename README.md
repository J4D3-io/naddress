NAddress
=================
NAddress is a Python library for parsing unstructured North American address strings into address components, using advanced NLP methods.

**What this can do:** 
Using a probabilistic model, it makes (very educated) guesses in identifying address components, even in tricky cases where rule-based parsers typically break down.

**What this cannot do:** 
- Identify address components with perfect accuracy.
- Verify that a given address is correct/valid.
- Normalize the address. 


## How to use this development code (for the nerds)
NAddress uses [parserator](https://github.com/datamade/parserator), a library for making and improving probabilistic parsers - specifically, parsers that use [python-crfsuite](https://github.com/tpeng/python-crfsuite)'s implementation of conditional random fields. Parserator allows you to train the NAddress parser's model (a .crfsuite settings file) on labeled training data, and provides tools for adding new labeled training data.


### Building & testing the code in this repo

To build a development version of usaddress on your machine, run the following code in your command line:
  ```
  git clone https://github.com/J4D3-io/naddress.git  
  cd naddress  
  pip install -e ."[dev]"
  ```  
Then run the testing suite to confirm that everything is working properly:
   ```
   pytest
   ```
   
Having trouble building the code? [Open an issue](https://github.com/datamade/usaddress/issues/new) and we'd be glad to help you troubleshoot.

### Adding new training data

If NAddress is consistently failing on particular address patterns, you can adjust the parser's behavior by adding new training data to the model. [Follow our guide in the training directory](./training/README.md), and be sure to make a pull request so that we can incorporate your contribution into our next release!


## Important links

* Repository: https://github.com/J4D3-io/naddress
* Issues: https://github.com/J4D3-io/naddress/issues


## Bad Parses / Bugs

Report issues in the [issue tracker](https://github.com/J4D3-io/naddress/issues)

If an address was parsed incorrectly, please let us know! You can either [open an issue](https://github.com/J4D3-io/naddress/issues/new) or (if you're adventurous) [add new training data to improve the parser's model.](./training/README.md) When possible, please send over a few real-world examples of similar address patterns, along with some info about the source of the data - this will help us train the parser and improve its performance.

If something in the library is not behaving intuitively, it is a bug, and should be reported.


## Note on Patches/Pull Requests
 
* Fork the project.
* Make your feature addition or bug fix.
* Send us a pull request. Bonus points for topic branches!


## Copyright

Copyright (c) 2025 Atlanta Journal Constitution. Released under the [MIT License](./LICENSE).
