---
Repo: https://github.com/wp-cli/profile-command
---
**Github Repository:** [WP Profile](https://github.com/wp-cli/profile-command/tree/v2.1.4)
**Install command** (WP-Cli v2.1)
**A handy usage guide:** [make.wordpress.org](https://make.wordpress.org/cli/handbook/how-to/figure-out-why-wordpress-is-slow/)

**What does it do?** 
- programmatically dissect WP loading process into segments (e.g: 'bootstrap', 'main query', 'template')
- Allows the user to drill down into specific segments and _decompose_ them into individual loading 'hooks' (i.e: `muplugins:before`, `setup_theme`, `wp_loaded:after`)
- 
**Known Defects:**
> Error:

Profiling intermediate hooks is broken in PHP 7, see https://bugs.php.net/bug.php?id=72966 kkk