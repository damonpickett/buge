# buge
*Think BUG-E, except I pronounce it 'booj'*

## Description

buge is a command-line application that helps developers understand and troubleshoot common error messages by generating explanations and solutions using the OpenAI GPT-3 language model.

## Instructions

1. Install buge by entering `pip3 install buge` in your terminal.
2. Call buge from anywhere in your terminal by entering `buge`.
3. If it's your first time calling buge, you will be prompted for you OpenAI API key. You'll only need to do this once.
4. You'll then be prompted for your error code. Paste you error code into your terminal and hit 'enter'.
5. buge makes an API call and then returns the the meaning of the error code, possible causes, and possible solutions.

This program is free to use. However, if you would like to <a href="https://www.buymeacoffee.com/damonpickett" target="_blank">buy me a coffee</a>, I would appreciate it :)

## Dependencies

- [OpenAI](https://pypi.org/project/openai/): A cloud-based platform that allows users to build various artificial intelligence models, including natural language processing models that can generate text.
- [python-dotenv](https://pypi.org/project/python-dotenv/): Python-dotenv reads key-value pairs from a .env file and can set them as environment variables. It helps in the development of applications following the [12-factor](https://12factor.net/) principles.
- [rich package](https://pypi.org/project/rich): Rich is a Python library for rich text and beautiful formatting in the terminal.

## How buge Works

1. Upon running the program, buge first checks your OpenAI API key in your `.env` file. If this file does not exist, buge prompts the user for their key, creates the file, and writes the key to the file. The .env file is then saved in the package folder.
2. buge then prompts the user for their error code.
3. buge takes the user's error code and passes it to the `get_error_explanation()` function as a parameter. This function makes three API calls based on the user's error code. It asks `text-davinci-003` for the meaning of the error code, possible causes for the error code, and possible solutions. It then prints the results to the user's console. I chose to use three seperate API calls as opposed to asking for everything at once to ensure that everything being asked for would be given its proper due by GPT-3. Bunching everything together in one prompt would have caused mixed results for users.

## Contributing

Contributions to BUGE are welcome! If you encounter any issues, have suggestions for improvements, or want to add new features, feel free to submit a pull request or open an issue in the [GitHub repository](https://github.com/damonpickett/buge).

## License

Copyright (c) 2018 The Python Packaging Authority

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.

## Disclaimer

Please note that BUGE is a tool that generates explanations and solutions based on a language model, and its suggestions should be used as a starting point for troubleshooting, not as definitive solutions. It's always recommended to thoroughly understand the error messages and the underlying code before making changes. BUGE is not responsible for any unintended consequences that may arise from using its generated explanations and solutions.