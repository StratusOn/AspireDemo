# Getting started with the AspireDemo solution

This demo adds a Chat Playground page to a basic .NET Aspire solution. It provides an experience similar to that of the `Chat Playground` feature in `Azure AI Foundry`.

The source code demonstrates using the *streaming* variant of the `completions` API to display the chat response fragments as they are received from the API call.

## Pre-requisites

1. Create a resource group. Name it something like `AI-RG`.

	Don't have an Azure account? Create a free account from https://azure.microsoft.com. The $200 credit allows for plenty of experimentation for a month.

2. In the resource group, create an `Azure OpenAI service` resource. Preferrably choose `EastUS2`, if there is enough quota.
3. Click on the created in step 2.
4. Click on the `Explore Azure AI Foundry portal`.
5. In `Azure AI Foundry`, click on `Deployments` in the left nav menu.
6. Click on `+ Deploy Model`. Click on `Deploy Base Model` from the dropdown.
7. Click on the model name. Copy the following pieces of information:
	a. `Endpoint subdomain`: It is usually `openai.azure.com` but could be `cognitiveservices.azure.com`.
	b. `Service name` (the name of the resource created in step 2)
	c. `Model name` (e.g. gpt-4.1)
	d. `Deployment name` (e.g. gpt-4.1)
	e. The `API key`
 
## Build the solution

1. Open the solution in `Visual Studio` (the free Community Edition can be used).
2. From the Build menu, choose `Build Solution`.
3. Run the solution (press `F5` key).

### Launch the Chat Playground sample

1. From the Aspire dashboard's `Resources` tab, click on the first link under the `Endpoints` column for the `webfrontend` row.
2. Click on `Chat Playground` from the left nav.
3. Plug the settings gathered in the `Pre-requisites` section above into the page's fields and click on the `Get Answer` button.
4. Modify the system prompt and test with different user prompts changing the `sampling temperature` between 0 and 2. Higher values enable more creative answers, but beware that as you get close to 2, the results can be unpredictable and non-deterministic (`LSD`-ish).