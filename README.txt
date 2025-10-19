Agent Interface Plugin

Make your WordPress site easy for AI agents to understand and browse.

This plugin creates a public manifest and provides clean JSON endpoints for your site’s content (Posts, Pages, and WooCommerce Products).
Instead of scraping your website, AI agents can now fetch structured data directly.

✨ Features

Public manifest at:

https://yoursite.com/.well-known/agent/manifest.json

JSON endpoints for:

Posts

Pages

WooCommerce Products (if WooCommerce is installed)

Optional Bearer Token protection for resources (manifest is always public)

Simple Settings page in WP Admin

🚀 Installation

Download the plugin ZIP.

In WordPress Admin → Plugins → Add New → Upload Plugin.

Upload the ZIP and click Activate.

In the left sidebar, click Agent Interface to configure.

⚙️ Configuration

From the Agent Interface settings page, you can:

Enable or disable Posts, Pages, Products

Turn on/off Bearer Token protection for non-manifest endpoints

Generate a new token if needed

🌐 Endpoints
Manifest (always public)

REST: https://yoursite.com/wp-json/agent/v1/manifest

Pretty: https://yoursite.com/.well-known/agent/manifest.json

Posts

List: https://yoursite.com/wp-json/agent/v1/resources/posts?limit=5

Single: https://yoursite.com/wp-json/agent/v1/resources/posts/{id}

Pages

List: https://yoursite.com/wp-json/agent/v1/resources/pages?limit=5

Single: https://yoursite.com/wp-json/agent/v1/resources/pages/{id}

Products (WooCommerce)

List: https://yoursite.com/wp-json/agent/v1/resources/products?limit=5

Single: https://yoursite.com/wp-json/agent/v1/resources/products/{id}

🔒 Token Mode

If Require Token is enabled in settings:
Add this header to requests for posts/pages/products:

Authorization: Bearer YOUR_TOKEN


Example:

curl -H "Authorization: Bearer YOUR_TOKEN" https://yoursite.com/wp-json/agent/v1/resources/posts?limit=5


The manifest itself is always public.
