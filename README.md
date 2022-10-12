# ArXiv-Daily-Mail-Alert

Daily ArXiv paper notification, customized keywords / authors filter.



## Launch

#### Step 1. Requirements

```shell
feedparser==5.2.1
```



#### Step 2. Set up the config.

In the demo.config, set up the sender, password, and receivers for mail notifications.

More importantly, set the keywords, categories, and authors that you want to keep track of.

**keywords**: return paper's **title** OR **abstract** contains at least one keyword of interest

**authors**: return paper's author list contains at least one author of interest

**categories**: return paper at least belongs to one of the named categories



Note that only papers that **met all above three factors** will be returned. Hence, to follow specific authors not limited to any keyword, simply leave the `keywords` list in the config.yaml blank. Similarly, to follow specific topics not limited to any author, leave the `authors` list bank.

So, you can make **two yamls** for separate authors and keywords following.



#### Step 3. Run

```shell
python --config_path [CONFIG_PATH]
```



#### Step 4. Run it Daily

Combined with [crontab](https://www.ibm.com/docs/en/aix/7.2?topic=c-crontab-command), you will be notified daily.

```shell
# e.g. every 9 am at workday send me two papers alerts, one contains authors of interest and another contains keywords of interest.
0 9 * * 1-5 cd ~/workspaces/tools/ArXiv-Daily-Mail-Alert/ && ~/anaconda3/bin/python arxiv_alert.py --config_path config-author.yaml
0 9 * * 1-5 cd ~/workspaces/tools/ArXiv-Daily-Mail-Alert/ && ~/anaconda3/bin/python arxiv_alert.py --config_path config-keyword.yaml
```



### Contact

If you have any questions, feel free to contact Kai Zhang `drogozhang@gmail.com` or open an issue, I will solve it as promptly as I can.
