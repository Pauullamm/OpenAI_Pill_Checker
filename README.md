# OpenAI_Pill_Checker

#### NOTE: This project is a demo and certain features are not optimized for AI training. Cleaning of data and validation datasets are needed to improve this project.

Problem:

There is currently no publicly available pill-identifying software which identifies tablets/capsules based on their appearance. Furthermore, there are no publicly available and up-to-date images of medicines that may be used to train image models. 
This project is a Jupyter notebook which handles text descriptions of tablets and capsules as an alternative.

## Usage

Select for medicines by alphabet from the [Electronic Medicines Compendium](https://www.medicines.org.uk/emc). This example uses medicines starting with the letter B

```bash
letter_B_url = 'https://www.medicines.org.uk/emc/browse-medicines/B'
```

Follow the steps of the notebook to generate JSONL data to be used to fine-tune an OpenAI model

```python
from openai import OpenAI
import openai

api_key = "YOUR OPENAI API KEY"

client = OpenAI(api_key=api_key)

training_file_id = client.files.create(
  file=open(training_file_name, "rb"),
  purpose="fine-tune"
)
```
Test your model using prompts:

![OpenAI Demo](https://github.com/Pauullamm/OpenAI_Pill_Checker/assets/109431478/b0fd22c1-617f-4e2d-860f-a0f342c8a67e)


## License

[MIT](https://choosealicense.com/licenses/mit/)
