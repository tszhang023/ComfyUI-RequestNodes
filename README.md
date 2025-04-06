# ComfyUI-RequestNodes

[中文版本](README_zh.md)

## Introduction

ComfyUI-RequestNodes is a custom node plugin for ComfyUI that provides functionality for sending HTTP requests. Currently, it includes the following nodes:

*   **Get Node**: Sends GET requests and retrieves responses.
*   **Post Node**: Sends POST requests and retrieves responses.
*   **Header Node**: Manages HTTP request headers.
*   **Key/Value Node**: Creates key/value pairs for building request parameters or headers.

## Test Resources

The plugin includes the following test resources:
* `base_flask_server.py` - Python Flask server for testing
* `get_node.json` - GET request workflow template
![7da7547075bfc89220dc8bff1f8c62f](https://github.com/user-attachments/assets/ce9e6f04-1618-433a-8d69-4857a280dc61)
![8b717a369b523e69385f50fe176ccf2](https://github.com/user-attachments/assets/b5f1795a-589d-43df-8e82-a1a079262e5f)
* `post_node.json` - POST request workflow template
![cd28f656ab8ae165db4095d325fa38d](https://github.com/user-attachments/assets/28ad21f5-2949-4c41-8d61-994b9170f37c)
![c7549268846ea3b570462c92acfb16c](https://github.com/user-attachments/assets/12dbd00b-af85-439d-978f-301760536005)

## Installation

To install ComfyUI-RequestNodes, follow these steps:

1.  **Open the ComfyUI custom_nodes directory.**
    *   In your ComfyUI installation directory, find the `custom_nodes` folder.

2.  **Clone the ComfyUI-RequestNodes repository.**
    *   Open a terminal or command prompt in the `custom_nodes` directory.
    *   Run the following command to clone the repository:

    ```bash
    git clone https://github.com/felixszeto/ComfyUI-RequestNodes.git
    ```

3.  **Restart ComfyUI.**
    *   Close and restart ComfyUI to load the newly installed nodes.

## Usage

After installation, you can find the "Get Node" and "Post Node" nodes under the "Request Nodes" category in the ComfyUI node list.

*   **Get Node**:
    *   **url**: Enter the URL address you want to request.
    *   **json_array**: Input JSON array generated by Key/Value Nodes as request parameters.
    *   **headers**: Input request headers generated by Header Node.
    *   **output_format**: Select the output format of the response, such as "text" or "json".
    *   **response**: Output response content.
    *   ![image](https://github.com/user-attachments/assets/cdb1938f-f8a9-4a4b-a787-90fa4d543523)


*   **Header Node**:
    *   **json_array**: Input JSON array generated by Key/Value Nodes as request headers.
    *   **output**: Output merged request headers.
    *   ![image](https://github.com/user-attachments/assets/832e4a4a-ffd5-42b2-bc3c-0c24f113c0bf)


*   **Key/Value Node**:
    *   **key**: Input key name.
    *   **value**: Input key value.
    *   **input_json**: Optional, connect output from other Key/Value Nodes.
    *   **output**: Output JSON array containing the key/value pair.
    *   ![image](https://github.com/user-attachments/assets/dfe7dab0-2b1b-4f99-ac6f-89e01d03b7e0)




*   **Post Node**:
    *   **url**: Enter the URL address you want to request.
    *   **data**: Enter the data for the POST request, in JSON format.
        *   In the `data` field, you can use placeholders like `__str1__`, `__str2__`, etc. in your JSON request body.
        *   These placeholders will be replaced by the values of input strings `str1`, `str2`, etc. respectively.
        *   For example, if you have an input string named `str1` with the value "example", and your JSON data is `{"key": "__str1__"}`, the actual request body will be `{"key": "example"}`.
    *   **output_format**: Select the output format of the response, such as "text" or "json".
    *   **response**: Output response content.
    *   ![image](https://github.com/user-attachments/assets/6eda9fef-48cf-478c-875e-6bd6d850bff2)



   
## Contribution

Welcome to submit issues and pull requests to improve ComfyUI-RequestNodes!

---

**Note:**

*   Please ensure that your ComfyUI environment has Git installed correctly.
*   If your ComfyUI installation directory is not in the default location, please adjust the path according to your actual situation.
*   If you encounter any problems, please check the issue page of the GitHub repository or submit a new issue.
