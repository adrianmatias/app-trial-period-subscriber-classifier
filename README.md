# App trial period subscriber classifier

One mobile app offers a monthly subscription with one week trial period (at the end of which, the customer starts paying the subscription, unless they cancel). Using a sample of data, the aim of this repository is to extract insights and build a model to predict if a user would become a paying customer or not at the end of trial.

## General overview of the app flow

Journey starts with installing the app on a user's device. When a user launches the app for the first time he needs to complete the onboarding. App asks for some information like the level or age of the children to personalize the experience. Right after, a paywall is shown. This is where user is ofered the chance to start a subscription with the mentioned 7 days trial period. After 7 days - and if they don’t cancel their subscription - they become paying customers and an invoice is recorded in the system. In the paywall they have the chance to not start a trial, so some users can use the app but in a limited way (would be a basic user). If they try to access features that are only available for paying customers, or if they reach daily limits, the paywall is shown again.

There is a key interest in knowing if a user would potentially convert into a customer after trial ends. Besides, knowing it as soon as possible in the trial period gives us some advantage to take other actions, so it is benefical to anticipate the prediction as much as possible, ideally in the first days of trial.

Main objectives are:

- Design and build a classification model that predicts if a user who has started a trial would become a paying customer.
- Provide some insights about which features have more impact in converting to customers.

## Data provided

- users_onboarding_paywall.tsv: information of user onboarding and subcription paywal users_onboarding_paywall.tsv
- activities_per_day.tsv: information of activities played during trial period.

All detailed info regarding structure and fields can be found here:

## How to reproduce analysis and use model

Is recommended to use `virtualenv` for development:

- Start by installing `virtualenv` if you don't have it
```
pip install virtualenv
```

- Once installed access the project folder
```
cd .../app-trial-period-subscriber-classifier
```

- Create a virtual environment
```
virtualenv venv
```

- Enable the virtual environment
```
source venv/bin/activate
```

- Install the python dependencies on the virtual environment
```
pip install -r requirements.txt
```

- Run the data profiling tool
```
python src/profile_data.py
```

- Launch jupyter lab
```
jupyter lab
```

- Run the notebooks
```
src/EDA.ipynb
src/subscriber_model.ipynb

```
