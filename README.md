{
  "nbformat": 4,
  "nbformat_minor": 0,
  "metadata": {
    "colab": {
      "name": "Untitled2.ipynb",
      "provenance": []
    },
    "kernelspec": {
      "name": "python3",
      "display_name": "Python 3"
    },
    "language_info": {
      "name": "python"
    }
  },
  "cells": [
    {
      "cell_type": "code",
      "metadata": {
        "colab": {
          "base_uri": "https://localhost:8080/"
        },
        "id": "Ls9_K2_sntcl",
        "outputId": "fb636f18-c752-48bb-d1af-31fdcb59ddd8"
      },
      "source": [
        "!pip install keras-tuner"
      ],
      "execution_count": 31,
      "outputs": [
        {
          "output_type": "stream",
          "text": [
            "Requirement already satisfied: keras-tuner in /usr/local/lib/python3.7/dist-packages (1.0.2)\n",
            "Requirement already satisfied: colorama in /usr/local/lib/python3.7/dist-packages (from keras-tuner) (0.4.4)\n",
            "Requirement already satisfied: numpy in /usr/local/lib/python3.7/dist-packages (from keras-tuner) (1.19.5)\n",
            "Requirement already satisfied: terminaltables in /usr/local/lib/python3.7/dist-packages (from keras-tuner) (3.1.0)\n",
            "Requirement already satisfied: scikit-learn in /usr/local/lib/python3.7/dist-packages (from keras-tuner) (0.22.2.post1)\n",
            "Requirement already satisfied: scipy in /usr/local/lib/python3.7/dist-packages (from keras-tuner) (1.4.1)\n",
            "Requirement already satisfied: future in /usr/local/lib/python3.7/dist-packages (from keras-tuner) (0.16.0)\n",
            "Requirement already satisfied: tqdm in /usr/local/lib/python3.7/dist-packages (from keras-tuner) (4.41.1)\n",
            "Requirement already satisfied: requests in /usr/local/lib/python3.7/dist-packages (from keras-tuner) (2.23.0)\n",
            "Requirement already satisfied: tabulate in /usr/local/lib/python3.7/dist-packages (from keras-tuner) (0.8.9)\n",
            "Requirement already satisfied: packaging in /usr/local/lib/python3.7/dist-packages (from keras-tuner) (20.9)\n",
            "Requirement already satisfied: joblib>=0.11 in /usr/local/lib/python3.7/dist-packages (from scikit-learn->keras-tuner) (1.0.1)\n",
            "Requirement already satisfied: certifi>=2017.4.17 in /usr/local/lib/python3.7/dist-packages (from requests->keras-tuner) (2020.12.5)\n",
            "Requirement already satisfied: chardet<4,>=3.0.2 in /usr/local/lib/python3.7/dist-packages (from requests->keras-tuner) (3.0.4)\n",
            "Requirement already satisfied: idna<3,>=2.5 in /usr/local/lib/python3.7/dist-packages (from requests->keras-tuner) (2.10)\n",
            "Requirement already satisfied: urllib3!=1.25.0,!=1.25.1,<1.26,>=1.21.1 in /usr/local/lib/python3.7/dist-packages (from requests->keras-tuner) (1.24.3)\n",
            "Requirement already satisfied: pyparsing>=2.0.2 in /usr/local/lib/python3.7/dist-packages (from packaging->keras-tuner) (2.4.7)\n"
          ],
          "name": "stdout"
        }
      ]
    },
    {
      "cell_type": "code",
      "metadata": {
        "id": "84pHxf22oBRK"
      },
      "source": [
        "import tensorflow as tf\n",
        "from tensorflow import keras\n",
        "import numpy as np"
      ],
      "execution_count": 32,
      "outputs": []
    },
    {
      "cell_type": "code",
      "metadata": {
        "id": "2swKX7rLoHBN"
      },
      "source": [
        "fashion_minst=keras.datasets.fashion_mnist"
      ],
      "execution_count": 33,
      "outputs": []
    },
    {
      "cell_type": "code",
      "metadata": {
        "id": "cZ86K84noMvo"
      },
      "source": [
        "(train_images,train_labels),(test_images,test_labels)=fashion_minst.load_data()"
      ],
      "execution_count": 34,
      "outputs": []
