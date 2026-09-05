# Configure AI providers and read their status

Use **PROVIDER CONFIGURATION** on the challenge setup screen to choose providers and models. The badges in the top navigation bar show status; they are not settings buttons. These instructions match the current application source.

## 1. Choose the providers you want to use

Expand **PROVIDER CONFIGURATION** if it is collapsed. Each provider has its own enable checkbox and model field.

| Provider card | Enable control | Model selection |
| --- | --- | --- |
| **OpenAI-compatible** | **Enable OpenAI-compatible API** | Enter a model available through your chosen compatible service. |
| **Ollama** | **Use Ollama for an independent agent** | Enter the desired tag in **MODEL / OLLAMA LIBRARY TAG**. |
| **Gemini (optional)** | **Enable Gemini API** | Enter a model available to your provider account. |

Enable only the providers you intend to use. Cloud providers receive the inputs sent to them and may charge for requests. Provider choices here apply to the configured agents; these cards are not separate Red/Blue assignment controls.

## 2. Configure a cloud provider

1. Enable its checkbox.
2. Check the **ENDPOINT** and **MODEL** against your service's connection instructions.
3. Enter your provider credential in its **API KEY** field.
4. Click **Save provider settings** and wait for the save to finish.
5. Check the provider's top-bar badge, then complete a small practice turn.

If a key is already saved, leaving its field blank keeps that key. To remove it, select the provider's **Clear saved … key** checkbox and save. Disabling a provider and removing its saved credential are separate actions.

## 3. Configure Ollama

1. Complete [[Offline-Ollama-Setup]] and make sure Ollama is running.
2. Enable **Use Ollama for an independent agent**.
3. Enter the model tag you intend to use. The field accepts a tag rather than requiring a choice from a short fixed list.
4. Use the model setup/download control shown in the Ollama card when the model needs to be installed. Allow the download to finish.
5. Save provider settings and run a small challenge to check the selection.

The displayed Ollama endpoint is read-only in this panel. If your installation requires a different connection setup, use the supported setup instructions or contact support. A model tag must identify an available model that your hardware can run; entering a tag alone does not install it. Downloads require an internet connection.

## 4. Read the navigation badges

| State | Meaning |
| --- | --- |
| **OFF** | The provider is disabled. |
| **NOT READY** | The provider is enabled but is not reported as configured and usable. |
| **READY** | The app reports the provider as configured. A successful practice turn confirms actual execution. |

If a provider remains **NOT READY**, check its enable state, model, required credential and service availability. Read any save or turn error before retrying.

## 5. Reset only when intended

**Reset saved settings** resets provider configuration; it is not a refresh button. Read its confirmation and be prepared to configure providers again. To stop using just one provider, clear its enable checkbox and save instead.

[[Navigation-and-Battle-Controls]] · [[Tutorial-Your-First-Arena-Battle]] · [[Home]]
