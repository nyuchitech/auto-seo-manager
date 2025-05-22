# Auto SEO Manager for WordPress

**Automated SEO optimization with Yoast integration, comprehensive meta tags, and social media optimization.**

[![WordPress](https://img.shields.io/badge/WordPress-5.0%2B-blue.svg)](https://wordpress.org/)
[![PHP](https://img.shields.io/badge/PHP-7.4%2B-purple.svg)](https://php.net/)
[![License](https://img.shields.io/badge/License-GPL%20v2-green.svg)](https://www.gnu.org/licenses/gpl-2.0.html)
[![Version](https://img.shields.io/badge/Version-1.0.0-orange.svg)](https://github.com/yourusername/auto-seo-manager)

## 🚀 Overview

Auto SEO Manager is a powerful WordPress plugin that automatically generates and manages SEO data for your entire website. It works seamlessly with Yoast SEO while adding comprehensive meta tags, Open Graph data, Twitter Cards, and advanced automation features.

### Key Features

- ✅ **Automated SEO Generation** - Titles, descriptions, and keywords
- ✅ **Comprehensive Meta Tags** - All essential SEO meta tags  
- ✅ **Social Media Optimization** - Open Graph and Twitter Cards
- ✅ **Yoast SEO Integration** - Works alongside existing Yoast data
- ✅ **Plugin Integrations** - WooCommerce, ACF, Elementor, Events Calendar, and more
- ✅ **Scheduled Automation** - Daily processing with external cron support
- ✅ **Integration Management** - Easy enable/disable for each plugin integration
- ✅ **Performance Optimized** - Batch processing for large sites
- ✅ **Monitoring & Logging** - Comprehensive activity tracking
- ✅ **Testing Tools** - Built-in validation and debugging utilities

## 📋 Requirements

- **WordPress**: 5.0 or higher
- **PHP**: 7.4 or higher  
- **Yoast SEO**: Required (free or premium)
- **Memory**: 128MB+ recommended
- **Server**: Apache/Nginx with mod_rewrite

## 🔧 Installation

### Method 1: Manual Installation

1. **Download** the latest release from GitHub
2. **Extract** the files to `/wp-content/plugins/auto-seo-manager/`
3. **Activate** the plugin through WordPress Admin → Plugins
4. **Configure** settings at Settings → Auto SEO Manager

### Method 2: WordPress Admin Upload

1. **Download** the plugin ZIP file
2. **Upload** via WordPress Admin → Plugins → Add New → Upload
3. **Activate** and configure

### Required Files Structure
```
/wp-content/plugins/auto-seo-manager/
├── auto-seo-manager.php          # Main plugin file
├── admin-page.php                # Admin interface
├── integrations.php              # Plugin integrations
├── meta-tags-test.php           # Testing utility
├── README.md                    # Documentation
└── LICENSE                      # GPL v2 License
```

## ⚙️ Configuration

### Basic Setup

1. **Enable Auto SEO**: Check the main enable checkbox
2. **Select Post Types**: Choose which content to process
3. **Configure Templates**: Set SEO title patterns
4. **Set Author Info**: Add your name and contact details
5. **Enable Features**: Turn on meta tags, Open Graph, Twitter Cards
6. **Configure Integrations**: Enable/disable plugin integrations as needed

### Plugin Integrations

Auto SEO Manager includes a comprehensive integration system with visual management:

#### Available Integrations

🛒 **WooCommerce Integration**
- Product-specific title templates with pricing placeholders
- Enhanced descriptions with inventory and pricing information
- Product category and attribute keyword extraction
- Schema markup for better search engine understanding

🔧 **Advanced Custom Fields (ACF) Integration**  
- Use custom fields for SEO descriptions (`seo_description`)
- Extract focus keywords from ACF fields (`seo_keywords`)
- Integrate summary and excerpt fields
- Support for custom meta data structures

🎨 **Elementor Integration**
- Extract text content from Elementor widgets and sections
- Parse page builder data for SEO content generation
- Enhanced SEO support for builder-created pages

🏗️ **Beaver Builder Integration**
- Content extraction from Beaver Builder layouts
- Widget text parsing and analysis
- Layout-aware SEO generation

📅 **The Events Calendar Integration**
- Event-specific title templates with date placeholders
- Venue information integration in descriptions
- Event meta data optimization
- Calendar-specific SEO enhancements

🌐 **WPML/Polylang Integration**
- Multi-language SEO template support
- Localized meta description generation
- Language-specific keyword extraction
- Regional SEO optimization

📝 **Gutenberg Blocks Integration**
- Advanced content extraction from block editor
- Block-specific text analysis
- Modern editor content parsing

📋 **Custom Post Type UI Integration**
- Support for custom post types and taxonomies
- Extended SEO templates for custom content
- Custom field integration and support

#### Integration Management

The plugin features a dedicated **Integrations tab** with:

- **Visual Plugin Cards**: See all available integrations at a glance
- **Toggle Switches**: Easy enable/disable for each integration
- **Status Indicators**: Clear visual feedback for plugin availability
- **Feature Lists**: Detailed information about each integration's capabilities
- **Installation Guidance**: Helper text for unavailable plugins
- **Integration Testing**: Built-in test tool to verify functionality

### Advanced Configuration

```php
// Custom title templates
$templates = array(
    'post' => '%%title%% | Expert Guide | %%sitename%%',
    'page' => '%%title%% | %%sitename%%',
    'product' => '%%title%% - Best Price | %%sitename%%'
);

// Available placeholders
%%title%%        // Post/page title
%%sitename%%     // Site name
%%currentdate%%  // Current year
%%category%%     // Primary category
%%location%%     // Business location (if set)
%%price%%        // Product price (WooCommerce)
```

### External Cron Setup

For reliable automation, set up server-level cron:

```bash
# Daily execution at 2 AM
0 2 * * * curl -s "https://yoursite.com/auto-seo-cron/YOUR-SECRET-KEY" > /dev/null
```

## 🎯 Usage

### Automatic Processing

The plugin automatically:

1. **Scans content daily** for missing SEO data
2. **Generates meta tags** using your templates and content analysis
3. **Creates social media tags** for better sharing
4. **Extracts keywords** from content, categories, and tags
5. **Logs all activities** for monitoring and debugging
6. **Sends weekly reports** with audit findings

### Manual Tools

- **Bulk Update**: Process all content immediately
- **Meta Preview**: See generated tags before publishing
- **Test Utility**: Comprehensive validation and debugging
- **Activity Monitor**: Track all plugin operations

### Generated Meta Tags

```html
<!-- Basic SEO -->
<meta name="description" content="Auto-generated description">
<meta name="keywords" content="extracted, keywords, here">
<meta name="author" content="Your Name">
<meta name="robots" content="index, follow">

<!-- Open Graph -->
<meta property="og:title" content="Page Title">
<meta property="og:description" content="Social description">
<meta property="og:image" content="Featured image URL">
<meta property="og:url" content="Page URL">

<!-- Twitter Cards -->
<meta name="twitter:card" content="summary_large_image">
<meta name="twitter:site" content="@yourusername">
<meta name="twitter:title" content="Page Title">
<meta name="twitter:description" content="Social description">
```

## 🔌 Plugin Integrations

### Supported Plugins

- **WooCommerce** - Enhanced product SEO with pricing and inventory
- **Advanced Custom Fields** - Use ACF fields for SEO data
- **Elementor** - Extract content from Elementor pages
- **Beaver Builder** - Page builder content extraction
- **The Events Calendar** - Event-specific SEO optimization
- **WPML/Polylang** - Multilingual SEO support
- **Custom Post Type UI** - Support for custom post types

### WooCommerce Integration

```php
// Product-specific placeholders
%%price%%           // Product price
%%sale%%            // "On Sale" if applicable
%%stock%%           // Stock status
%%product_category%% // Primary product category

// Example product title template
'product' => '%%title%% - %%price%% | %%product_category%% | %%sitename%%'
```

**Enhanced Product SEO Features:**
- Automatic pricing information in titles and descriptions
- Product category and attribute keyword extraction
- Inventory status integration ("In Stock" / "Out of Stock")
- Schema markup for rich search results
- Sale status highlighting in meta descriptions

### Advanced Custom Fields Integration

```php
// Supported ACF field names
seo_description    // Custom meta description
seo_keywords      // Focus keywords
focus_keywords    // Alternative keyword field
summary           // Page summary content
excerpt           // Custom excerpt field
```

**ACF Integration Benefits:**
- Priority given to ACF fields over auto-generated content
- Seamless integration with existing ACF setups
- Support for complex field structures
- Custom content prioritization

### Events Calendar Integration

```php
// Event-specific placeholders
%%event_date%%    // Event start date
%%event_venue%%   // Venue name
%%event_time%%    // Event time

// Example event title template
'tribe_events' => '%%title%% | %%event_date%% at %%event_venue%% | %%sitename%%'
```

### Integration Management Interface

The plugin includes a visual integration management system:

1. **Automatic Detection**: Scans for installed and active plugins
2. **Visual Cards**: Each integration displayed in organized cards
3. **Toggle Controls**: Easy enable/disable switches
4. **Status Indicators**: Clear availability and activation status
5. **Testing Tools**: Built-in integration testing functionality
6. **Feature Documentation**: Detailed capability descriptions

### Custom Integrations

Developers can add custom integrations:

```php
// Register custom integration
auto_seo_register_integration('my_plugin', function() {
    add_filter('auto_seo_title_generation', 'my_custom_titles', 10, 2);
    add_filter('auto_seo_meta_description', 'my_custom_descriptions', 10, 2);
});
```

## 🔍 Testing & Debugging

### Built-in Test Utility

Access the comprehensive testing tool:
```
yoursite.com/wp-admin/admin.php?page=auto-seo-manager&test_meta=1
```

**Test Features:**
- Plugin status verification
- Sample meta tag generation
- Performance benchmarking
- Configuration validation
- Conflict detection
- Integration testing

### Integration Testing

The plugin includes built-in integration testing:

1. **Go to Settings** → Auto SEO Manager → **Tools tab**
2. **Click "Test Integrations"** button
3. **Review results** for each available integration:
   - ✅ **Active**: Plugin installed and integration enabled
   - ⏸️ **Available but Disabled**: Plugin installed but integration disabled
   - ❌ **Not Available**: Plugin not installed or activated

### Admin Interface Testing

**Settings Tab:**
- Basic plugin configuration
- Meta tags settings
- Social media options

**Integrations Tab:**
- Visual plugin detection
- Enable/disable toggles
- Integration status overview
- Feature documentation

**Activity Log Tab:**
- Plugin operation history
- Integration initialization logs
- Error tracking and reporting

**Tools Tab:**
- Manual update execution
- Meta preview functionality
- Integration testing
- System information display

### Debugging Tips

```php
// Enable WordPress debugging
define('WP_DEBUG', true);
define('WP_DEBUG_LOG', true);

// Check plugin logs
tail -f /wp-content/debug.log | grep "Auto SEO"

// Test meta generation manually
do_action('daily_seo_update');
```

## 📊 Performance & Optimization

### Performance Features

- **Batch Processing**: Handles large sites efficiently
- **Memory Management**: Dynamic batch sizing based on available resources
- **Caching Integration**: Works with popular caching plugins
- **Database Optimization**: Indexed logging table for fast queries

### Recommended Settings

```php
// Large sites (1000+ posts)
Batch Size: 25-50 posts
Memory Limit: 256MB+
Execution Time: 300 seconds

// Small-medium sites (<1000 posts)  
Batch Size: 50-100 posts
Memory Limit: 128MB+
Execution Time: 60 seconds
```

## 🛡️ Security

### Security Features

- **Nonce verification** for all admin actions
- **Capability checks** for user permissions
- **Input sanitization** for all settings
- **Secret cron keys** for external automation
- **SQL injection prevention** with prepared statements

### Best Practices

- Keep WordPress and plugins updated
- Use strong admin passwords
- Limit admin access appropriately
- Monitor activity logs regularly
- Use HTTPS for all admin operations

## 🔧 Troubleshooting

### Common Issues

**Plugin not generating meta tags:**
- Verify Yoast SEO is active
- Check that "Auto Additional Meta" is enabled
- Ensure post types are selected in settings
- Run manual update to test

**Performance issues:**
- Reduce batch size in settings
- Increase PHP memory limit
- Use external cron instead of WordPress cron
- Check for plugin conflicts

**Social media sharing not working:**
- Verify OG image URLs are accessible
- Check image dimensions (1200x630px minimum)
- Test with Facebook Debugger and Twitter Card Validator
- Clear social media caches

**Cron not running:**
- Verify external cron URL format
- Check server cron job syntax
- Test URL manually in browser
- Check server error logs

### Debug Mode

```php
// Add to wp-config.php for detailed logging
define('AUTO_SEO_DEBUG', true);

// Check database for logged activities
SELECT * FROM wp_auto_seo_log ORDER BY timestamp DESC LIMIT 20;
```

## 🤝 Contributing

We welcome contributions from the community! See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

### Development Setup

```bash
# Clone repository
git clone https://github.com/yourusername/auto-seo-manager.git

# Set up local WordPress environment
cd auto-seo-manager
wp server --host=localhost --port=8080

# Install development dependencies
composer install
npm install
```

### Code Standards

- Follow WordPress coding standards
- Include PHPDoc comments
- Add unit tests for new features
- Update documentation

## 📝 Changelog

### Version 1.0.0 (2025-01-XX)

**🎉 Initial Release**

**Added:**
- Core SEO automation engine with Yoast integration
- Comprehensive meta tags generation (description, keywords, author, robots)
- Open Graph and Twitter Cards support for social media optimization
- Visual plugin integration system with 8+ supported plugins
- Scheduled automation with external cron support
- Professional admin interface with 4-tab navigation (Settings, Integrations, Activity Log, Tools)
- Advanced integration management with toggle controls
- Activity logging and monitoring system
- Built-in testing and debugging utilities
- Performance optimization with batch processing
- WooCommerce integration with product-specific SEO enhancements
- Advanced Custom Fields integration for custom SEO data
- Page builder support (Elementor, Beaver Builder)
- Events Calendar integration with event-specific optimization
- Multi-language support (WPML/Polylang)
- Custom Post Type UI integration

**Integration Features:**
- Visual plugin detection and status indicators
- Individual integration enable/disable controls
- Integration testing and validation tools
- Comprehensive feature documentation for each integration
- Smart loading system (only loads enabled integrations)
- Integration activity logging and monitoring

**Admin Interface:**
- Modern card-based integration management
- Toggle switches for easy control
- Real-time status updates
- Integration test functionality
- Comprehensive system information display

**Technical Details:**
- WordPress 5.0+ compatibility
- PHP 7.4+ requirement
- Database schema version 1.0
- 8+ plugin integrations included
- Comprehensive security implementations
- Performance-optimized batch processing

### Upcoming Features (v1.1.0)

**Planned Additions:**
- Enhanced schema.org markup generation with integration-specific schemas
- Google Search Console API integration for performance monitoring
- Advanced keyword research tools with competitor analysis
- A/B testing framework for meta tag optimization
- Enhanced multilingual features with RTL language support
- REST API endpoints for headless WordPress implementations
- WP-CLI commands for developers and automation
- Additional plugin integrations (LearnDash, GiveWP, Easy Digital Downloads)
- Advanced analytics and reporting dashboard
- Custom integration builder for developers

## 📄 License

This plugin is licensed under the [GPL v2 or later](https://www.gnu.org/licenses/gpl-2.0.html).

```
Auto SEO Manager WordPress Plugin
Copyright (C) 2025 Your Name

This program is free software; you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation; either version 2 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with this program; if not, write to the Free Software
Foundation, Inc., 51 Franklin St, Fifth Floor, Boston, MA 02110-1301 USA
```

## 👥 Credits

**Author**: Your Name  
**Contributors**: [Contributors List](https://github.com/yourusername/auto-seo-manager/contributors)  
**Inspiration**: WordPress community and SEO best practices

## 📞 Support

- **Documentation**: [GitHub Wiki](https://github.com/yourusername/auto-seo-manager/wiki)
- **Issues**: [GitHub Issues](https://github.com/yourusername/auto-seo-manager/issues)
- **Discussions**: [GitHub Discussions](https://github.com/yourusername/auto-seo-manager/discussions)
- **Support Forum**: [WordPress.org Support](https://wordpress.org/support/plugin/auto-seo-manager)

## 🌟 Show Your Support

If this plugin has helped your website's SEO, please:

- ⭐ Star the repository on GitHub
- 📝 Leave a review on WordPress.org
- 🐛 Report bugs and suggest features
- 💡 Contribute code improvements
- 📢 Share with the WordPress community

---

**Made with ❤️ for the WordPress community**
