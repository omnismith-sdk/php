# Omnismith PHP SDK

[![npm version](https://img.shields.io/npm/v/@omnismith%2Fsdk-typescript)](https://www.npmjs.com/package/@omnismith/sdk-typescript)
[![PyPI version](https://img.shields.io/pypi/v/omnismith-sdk-python)](https://pypi.org/project/omnismith-sdk-python/)
[![Packagist version](https://img.shields.io/packagist/v/omnismith/omnismith-sdk-php)](https://packagist.org/packages/omnismith/omnismith-sdk-php)
[![Go Report Card](https://goreportcard.com/badge/github.com/omnismith/omnismith-sdk-go)](https://goreportcard.com/report/github.com/omnismith/omnismith-sdk-go)

The Omnismith PHP SDK is generated from the central OpenAPI contract for the [Omnismith platform](https://omnismith.io), a flexible data management system built around templates, entities, and attribute-driven schemas. Use it to automate workflows against the Omnismith API and pair it with the web app at [app.omnismith.io](https://app.omnismith.io).

## Quick Start

```php
<?php

require_once __DIR__ . '/vendor/autoload.php';

use GuzzleHttp\Client;
use Omnismith\Api\EntityApi;
use Omnismith\Api\TemplatesApi;
use Omnismith\Configuration;
use Omnismith\Model\CreateEntityRequest;

$configuration = Configuration::getDefaultConfiguration()
    ->setHost('https://api.omnismith.io/v1')
    ->setAccessToken(getenv('OMNISMITH_ACCESS_TOKEN'));

$httpClient = new Client();
$templatesApi = new TemplatesApi($httpClient, $configuration);
$entityApi = new EntityApi($httpClient, $configuration);

$templateId = 'your-template-id';
$template = $templatesApi->getTemplate($templateId);

$entity = $entityApi->createEntity(
    new CreateEntityRequest([
        'template_id' => $template->getId(),
        'attribute_values' => [
            [
                'attribute_id' => $template->getAttributeIds()[0],
                'value' => 'SKU-1001',
            ],
        ],
    ])
);

printf("%s %s\n", $template->getName(), $entity->getId());
```

Set `OMNISMITH_ACCESS_TOKEN` to an access token created in Omnismith before running the snippet.