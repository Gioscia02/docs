# Logging System

The `CCAT_LOG_LEVEL` environment variable is used to manage the default logging level of the Cat. Take a look at Cat's environment variable [here](/production/administrators/env-variables/#ccat_log_level).

The available values for *level* are:

- **DEBUG**
- **INFO**
- **WARNING**
- **ERROR**
- **CRITICAL**

Logging messages which are less severe than *level* will be ignored; logging messages which have severity *level* or higher will be emitted to the console.

## How to

The logging system can be imported like this

```python
from cat.log import log
```

and then used as easy as:

```python
log.error("A simple text here")
log.info(f"Value of user message is {user_message_json["text"]}")
log.critical(variable_value)
```

Take a look [here](https://cheshire-cat-ai.github.io/docs///API_Documentation/log/) if you want to better understand how the log system is implemented.

## Examples

Follows an example of the console log for each log level.

### DEBUG

- what you write in the code:

    ```python
    log.debug(f'user message: {user_message_json["text"]}')
    ```

- what the console logs:

    <span style="color:#2aa1b3;">cheshire_cat_core  |</span> <span style="color:#26a269;">[2024-01-20 17:40:23.816]</span> <span style="color:#12488b;">DEBUG</span> <span style="color:#2aa1b3;">cat.plugins.cat-formatter.cat_formatter..before_cat_reads_message::26</span> => <span style="color:#12488b;">'user message: The answer to all questions is 42.'</span>

### INFO

- what you write in the code:

    ```python
    log.info(f'user message: {user_message_json["text"]}')
    ```

- what the console logs:

    <span style="color:#2aa1b3;">cheshire_cat_core  |</span> <span style="color:#26a269;">[2024-01-20 17:42:19.609]</span> INFO <span style="color:#2aa1b3;">cat.plugins.cat-formatter.cat_formatter..before_cat_reads_message::26</span> => 'user message: The answer to all questions is 42.'

### WARNING

- what you write in the code:

    ```python
    log.warning(f'user message: {user_message_json["text"]}')
    ```

- what the console logs:

    <span style="color:#2aa1b3;">cheshire_cat_core  |</span> <span style="color:#26a269;">[2024-01-20 17:59:05.336]</span> <span style="color:#a2734c;">WARNING</span> <span style="color:#2aa1b3;">cat.plugins.cat-formatter.cat_formatter..before_cat_reads_message::26</span> => <span style="color:#a2734c;">'user message: The answer to all questions is 42.'</span>

### ERROR

- what you write in the code:

    ```python
    log.error(f'user message: {user_message_json["text"]}')
    ```

- what the console logs:

    <span style="color:#2aa1b3;">cheshire_cat_core  |</span> <span style="color:#26a269;">[2024-01-20 18:08:06.412]</span> <span style="color:#c01c28;">ERROR</span> <span style="color:#2aa1b3;">cat.plugins.cat-formatter.cat_formatter..before_cat_reads_message::26</span> => <span style="color:#c01c28;">'user message: The answer to all questions is 42.'</span>

### CRITICAL

- what you write in the code:

    ```python
    log.critical(f'user message: {user_message_json["text"]}')
    ```

- what the console logs:

    <span style="color:#2aa1b3;">cheshire_cat_core  |</span> <span style="color:#26a269;">[2024-01-20 18:11:24.992]</span> <span style="background-color:#c01c28;color:#ffffff;">CRITICAL</span> <span style="color:#2aa1b3;">cat.plugins.cat-formatter.cat_formatter..before_cat_reads_message::26</span> => <span style="background-color:#c01c28;color:#ffffff;">'user message: The answer to all questions is 42.'</span>
