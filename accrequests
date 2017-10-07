from wikitools import *
import json
import re
import threading
import thread
import time
import datetime
import userpass

site = wiki.Wiki()
site.login(userpass.username, userpass.password)
update = page.Page(site, 'User:Dane/accrequests')
template_path = "/data/project/dane/Tasks/acc/accrequests.txt"
    

def main():
    while 0 < 1:
        ammount = urllib2.request("pagewithvar")['nameofvar'] #If uses json (xml also works I believe)
        if is_edit_necessary(update, amount):
            update_template(update, amount)
        else:
            pass
        time.sleep(1800)

def is_edit_necessary(update, amount):
        current_lvl = pages_to_level(amount)
        onwiki_level_match = re.search("level\s*=\s*(\d+)",
                                       update.getWikiText())
        if onwiki_level_match:
                onwiki_level = int(onwiki_level_match.group(1))
                return onwiki_level != current_lvl
        else:
                return True

def update_template(update, amount):
        level = pages_to_level(amount)
        try:
                template = open(template_path)
        except IOError as e:
                print(e)
        try:
            template_page.edit(newtext = amount) #amount referring to amount of ACC requests
        except Exception as e:
            print(e)
        finally:
            template.close()
        
if __name__ == "__main__":
        main()
