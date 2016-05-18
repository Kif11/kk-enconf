# EnConf

EnConf is Python environmental variable configutrator. Support groups, multiple appends and nested variables.

Have you ever thought about to do better a job for your environment setup? Is this looks ugly to you? :unamused:

> os.environ['PYTHONPATH'] = os.environ['PYTHONPATH'] + os.path + os.path.normpath('/my/path')


EnConf can do better. Configure your production environment from an YAML file:
```python
from enconf import EnConf

env_config = EnConf()
env_config.from_file('/path/to/your/yaml/conf')
```

Here is an example of possible yaml configuration file:
```yaml
Global: !omap
    SETTINGS: /My/Tools/Settings
    SHOWS: /Projects/Python
    PYTHONPATH:
        - <PYTHONPATH>
        - <SETTINGS>/Python/common
        - <SETTINGS>/Python/common/darwin

Nuke: !omap
    FOUNDRY_LICENSE_FILE: 111.crest.com
    foundry_LICENSE: app.crest.com
    NUKE_EXTRA: <SETTINGS>/nuke/nuke_EEP
    NUKE_PATH:
        - <NUKE_PATH>
        - <NUKE_EXTRA>/gizmos
```


