お使いの端末によっては改造できません
Androidは対応していません
お問い合わせは、作成者のホームページまでお願いします
https://nanoka-1.jimdosite.com/
ログイン起動時にかたまることがあります
申し訳ございませんが、アップデートのため、お住まいの地域のMC2サイトは現在アクセスできません。サーバーが回復したら、すぐにお知らせします。中国語版では、すべてのサービスがタイムアウトされ、稼働していません。インターネットに精通した日本人視聴者は、ネットワークジェネレータを使ってサーバーを回復しようとするべきだ。それでも回復できない場合、インターネット担当者(#929839)に連絡してください。このサイトは日本MC2株式会社が運営しています。香港市民計画センターにある中国センターを見学してください。中国語版は30日後に閉まります。中国がコロナウイルスを誘発したことを認めない限り、それは回復しないはずだ。
很抱歉，由于更新，您所在地区的 MC2 站点目前无法访问。当服务器恢复时，我们会立即通知您。在中文版中，所有服务都已超时且未运行。 熟悉网络的日本观众应该尝试使用网络生成器恢复服务器。 如果还是不能恢复，请联系网络负责人（#929839）。 本网站由日本MC2株式会社运营。 请参观位于香港市民计划中心的中国中心。中文版将在 30 天后关闭。除非它承认是中国造成了冠状病毒，否则它不会恢复。

MODULES
from replit import db
from getkey import getkey
from guide import guide_txt
from news import *
import os
import timeit
import random

# FUNCTIONS
def rgb(r,g,b):
  return f"\033[38;2;{r};{g};{b}m"

def clear():
  os.system('clear')

def redeem_code():
  redeemcode1 = "COOKIES4LIFE"
  redeemcode2 = "TASTYDOUGH"
  redeemcode3 = "COOKIEMONSTA"

def sort_shop():
  for item in shop:
    if cookies < item.cost:
      break

  index = shop.index(item)

  if index <= 4:
    return shop[:5]

  elif cookies >= 1000000000000:
    return shop[-5:]

  return shop[index-3:index+2]

# STYLES
bold = "\033[1m"
underline = "\033[4m"
italic = "\033[3m"
darken = "\033[2m"
invisible = "\033[08m"
reverse = "\033[07m"
reset = "\033[0m"

light_blue = rgb(82,180,255)
light_brown = rgb(190,140,100)
brown = rgb(170,120,80)
golden = rgb(219,180,107)

# STATS
username = os.environ['REPL_OWNER']

upgrades = []
cookies = 0

reset_cps = True # flag for CPS

headline = f"Welcome back, {username}!"

golden_cookie = 0
golden_cookie_content = ""

if username == 'five-nine':
  print("Login to Replit to play this game.")

  exit()

if username not in db:
  db[username] = cookies

else:
  cookies = db[username]

#SHOP
class Upgrade:
  def __init__(self, name, cost, cps, cpc):
    self.name = name

    self.cost = cost
    
    self.cps = cps # cookies per second
    self.cpc = cpc # cookies per click

  def update_cost(self):
    self.cost += int(self.cost/6)

Cursor = Upgrade('Cursor', 15, 0.1, 0)
Grandma = Upgrade('Grandma', 100, 1, 0)
Fingers = Upgrade('Fingers', 400, 1, 1)
Farm = Upgrade('Farm', 1100, 8, 1)
Mine = Upgrade('Mine', 12000, 47, 1)
Factory = Upgrade('Factory', 130000, 260, 2)
Bank = Upgrade('Bank', 1400000, 1400, 0)
Temple = Upgrade('Temple', 2000000, 7800, 1)
Wizard_Tower = Upgrade('Wizard Tower', 330000000, 44000, 4)
Shipment = Upgrade('Shipment', 5100000000, 260000, 0)
Alchemy_Lab = Upgrade('Alchemy Lab', 75000000000, 1600000, 3)
Portal = Upgrade('Portal', 1000000000000, 10000000, 6)
Time_Machine = Upgrade('Time Machine', 14000000000000, 65000000, 6)
Cookie_Monster = Upgrade('Cookie Monster', 180000, 350, 70)
Blaster = Upgrade('Blaster', 20000000, 0, 3500)

shop = [Cursor,Grandma,Fingers,Farm,Mine,Factory,Bank,Temple,Wizard_Tower,Shipment,Alchemy_Lab,Portal,Time_Machine,Cookie_Monster,Blaster]

print(f"""\n{light_brown}░█████╗░░█████╗░░█████╗░██╗░░██╗██╗███████╗
██╔══██╗██╔══██╗██╔══██╗██║░██╔╝██║██╔════╝
██║░░╚═╝██║░░██║██║░░██║█████═╝░██║█████╗░░
██║░░██╗██║░░██║██║░░██║██╔═██╗░██║██╔══╝░░
╚█████╔╝╚█████╔╝╚█████╔╝██║░╚██╗██║███████╗
░╚════╝░░╚════╝░░╚════╝░╚═╝░░╚═╝╚═╝╚══════╝

{brown}░█████╗░██╗░░░░░██╗░█████╗░██╗░░██╗███████╗██████╗░
██╔══██╗██║░░░░░██║██╔══██╗██║░██╔╝██╔════╝██╔══██╗
██║░░╚═╝██║░░░░░██║██║░░╚═╝█████═╝░█████╗░░██████╔╝
██║░░██╗██║░░░░░██║██║░░██╗██╔═██╗░██╔══╝░░██╔══██╗
╚█████╔╝███████╗██║╚█████╔╝██║░╚██╗███████╗██║░░██║
░╚════╝░╚══════╝╚═╝░╚════╝░╚═╝░░╚═╝╚══════╝╚═╝░░╚═╝{reset}
      
Made by {light_blue}@UltimateCoder40{reset}, {light_blue}@CodingElf66{reset}, {light_blue}@PhantomPython{reset}, {light_blue}@rickysong{reset}, and {light_blue}@SilentFoxy78{reset}, and {light_blue}@JakeHu2020\n""")

print("Press [ENTER] to start the game\nPress [G] for guide\n")

keyInput = getkey()

clear()

if keyInput.lower() == 'g':
  print(guide_txt)

  input('\nPress [ENTER] to continue')

clear()

# GAME
while True: # loop forever
  shop_list = sort_shop()

  news_change = random.randint(1,10)
  
  if news_change == 1:
    if cookies < 100:
      headline = random.choice(starter_news)

    elif cookies >= 100 and cookies < 1000:
      headline = random.choice(intermediate_news)

    elif cookies >= 1000 and cookies < 15000:
      headline = random.choice(pro_news)

    elif cookies >= 15000 and cookies < 200000:
      headline = random.choice(legendary_news)

    else:
      headline = random.choice(mythical_news)
  
  if reset_cps:
    cps_start = timeit.default_timer()
  
  cps = 0
  cpc = 1
  
  items = len(upgrades)
  
  for upgrade in upgrades:
    cps += upgrade.cps
  
  for upgrade in upgrades:
    cpc += upgrade.cpc

  cps = round(cps,1)
  cpc = round(cpc,1)

  cookies = round(cookies,2)

  print(f"""\n                {bold}{light_brown}Cookie {brown}Clicker 🍪{reset}                 {bold}Stats 📈{reset}
    ───────────────────────────────────────────────────────────────────────────────
           {bold}{cookies} 🍪{reset}{(36-len(str(cookies)))*' '}{bold}CPS:{reset} {cps} (cookies per second)
                                                  {bold}CPC:{reset} {cpc} (cookies per click)
                                                  {bold}Items:{reset} {items}
          
          
                    {bold}Shop 🛒{reset}                       {bold}News 📰{reset}
    ───────────────────────────────────────────────────────────────────────────────
          {bold}[1]{reset} {shop_list[0].name}: {shop_list[0].cost} 🍪{(23-len(shop_list[0].name)-len(str(shop_list[0].cost)))*' '}{bold}{headline[:35]}{reset}        
          {bold}[2]{reset} {shop_list[1].name}: {shop_list[1].cost} 🍪{(23-len(shop_list[1].name)-len(str(shop_list[1].cost)))*' '}{bold}{headline[35:]}{reset}
          {bold}[3]{reset} {shop_list[2].name}: {shop_list[2].cost} 🍪
          {bold}[4]{reset} {shop_list[3].name}: {shop_list[3].cost} 🍪{(23-len(shop_list[3].name)-len(str(shop_list[3].cost)))*' '}{golden_cookie_content}
          {bold}[5]{reset} {shop_list[4].name}: {shop_list[4].cost} 🍪

        
                                    {bold}Leaderboard 🏆{reset}
    ───────────────────────────────────────────────────────────────────────────────
          🥇 {bold}Martinez10:{reset} 4.3235e+33 🍪
          🥈 {bold}twinnturbo:{reset} 3.62265e+22 🍪
          🥉 {bold}GreenHexagon:{reset} 2.56e+22 🍪

        
                        {bold}Make sure to press [S] to save your progress!{reset}""")

  
  start = timeit.default_timer()
    
  click = getkey()
  
  end = timeit.default_timer()
   
  if click == "\n" and end - start > 0.04: # prevent spam
    cookies += cpc
        
    for upgrade in upgrades:
      cookies += upgrade.cpc

  elif click in ['1','2','3','4','5']:
    index = int(click)-1

    upgrade = shop_list[index]

    if cookies >= upgrade.cost:
      cookies -= upgrade.cost
      
      upgrades.append(upgrade)

      upgrade.update_cost()

  elif click.lower() == 'g' and golden_cookie == 1 and end - start > 0.04: # prevent spam
    amount = int(cookies/(4/3))

    cookies += amount

  elif click.lower() == 's':
    db[username] = cookies

  cps_end = timeit.default_timer()

  if cps_end - cps_start >= 1:
    times = cps_end - cps_start

    cookies += times * cps

    reset_cps = True

  else:
    reset_cps = False

  golden_cookie = random.randint(1,100)

  if golden_cookie == 1:
    golden_cookie_content = f"{golden}[G] GOLDEN COOKIE!!!{reset}"

  else:
    golden_cookie_content = ""

  if '.0' == str(cookies)[-2:]:
    cookies = int(str(cookies)[:-2])

  clear()
Fortnite
email                     : ボット用アカウントのメールアドレス。 複数設定可能
owner                     : 所有者として設定したいユーザーの名前またはID
platform                  : ボットのプラットフォーム。 後述
outfit                    : ボットの初期コスチューム。名前かID
outfit_style              : ボットの初期コスチュームのスタイル
backpack                  : ボットの初期バックアクセサリー。名前かID
backpack_style            : ボットの初期バックアクセサリーのスタイル
pickaxe                   : ボットの初期収集ツール。名前かID
pickaxe_style             : ボットの初期収集ツールのスタイル
emote                     : ボットの初期エモート。名前かID
playlist                  : ボットの初期プレイリストのID
banner                    : ボットの初期バナーのID
banner_color              : ボットの初期バナーの色ID
avatar_id                 : ボットの初期アバターのID。後述
avatar_color              : ボットの初期アバターの色。後述
level                     : ボットの初期レベル
tier                      : ボットの初期ティア
xpboost                   : ボットの初期XPブースト
friendxpboost             : ボットの初期フレンドXPブースト
status                    : ボットの初期ステータス。 変数が使える。 後述
privacy                   : ボットの初期のプライバシー。 後述
whisper                   : ボットが囁きからコマンドを受け付けるかどうか。 true か false
partychat                 : ボットがパーティーチャットからコマンドを受け付けるかどうか。 true か false
disablewhisperperfectly   : 囁きが無効の場合、所有者も使えなくするかどうか
disablepartychatperfectly : パーティーチャットが無効の場合、所有者も使えなくするかどうか
joinemote                 : ボットのパーティーに誰かが参加した時にエモートを踊りなおすかどうか。 true か false
click_invite              : 'ここをクリックして招待'を送信するかどうか。 true か false
disable_voice             : パーティーのボイスチャットを無効化するかどうか。 true か false
ignorebot                 : ボットからのコマンドを無視するかどうか。 true か false
joinmessage               : ボットのパーティーに誰かが参加した時のメッセージ。 \n で改行。 変数が使える。 後述
randommessage             : ボットのパーティーに誰かが参加した時のランダムメッセージ。 \n で改行。 変数が使える。 後述
joinmessageenable         : ボットのパーティーに誰かが参加した時にメッセージを出すかどうか。 true か false
randommessageenable       : ボットのパーティーに誰かが参加した時にランダムメッセージを出すかどうか。 true か false
outfitmimic               : 他人のコスチュームを真似るかどうか。 true か false か ユーザーの名前またはID
backpackmimic             : 他人のバックアクセサリーを真似るかどうか。 true か false か ユーザーの名前またはID
pickaxemimic              : 他人の収集ツールを真似るかどうか。 true か false か ユーザーの名前またはID
emotemimic                : 他人のエモートを真似るかどうか。 true か false か ユーザーの名前またはID
mimic-ignorebot           : ボットユーザーは真似ないかどうか。 true か false
mimic-ignoreblacklist     : ブラックリストのユーザーは真似ないかどうか。 true か false
outfitlock                : コスチュームをロックするかどうか。 true か false
backpacklock              : バックアクセサリーをロックするかどうか。 true か false
pickaxelock               : 収集ツールをロックするかどうか。 true か false
emotelock                 : エモートをロックするかどうか。 true か false
acceptinvite              : ボットが招待を承諾するかどうか。 所有者からの招待は常に承諾 true か false
acceptfriend              : ボットがフレンド申請を承諾するかどうか。 true か false か null
addfriend                 : ボットがパーティーメンバーにフレンド申請を送るかどうか。 true か false
invite-ownerdecline       : ボットの所有者がパーティーにいるときに招待を拒否するかどうか。 true か false
inviteinterval            : 招待を承諾した後intervalの秒数だけ招待を拒否するようにするかどうか。 true か false
interval                  : 招待を承諾した後招待を拒否する秒数
waitinterval              : waitコマンドで招待を拒否する秒数
hide-user                 : パーティーに参加したユーザーを非表示にするかどうか。 true か false
hide-blacklist            : パーティーに参加したブラックリストのユーザーを非表示にするかどうか。 true か false
show-owner                : hide-userがtrueのときに所有者を表示するかどうか。 true か false
show-whitelist            : hide-userがtrueのときにホワイトリストのユーザーを表示するかどうか。 true か false
show-bot                  : hide-userがtrueのときにボットを表示するかどうか。 true か false
blacklist                 : ブラックリストに指定するユーザーのリスト。 ユーザー名かユーザーID
blacklist-declineinvite   : ブラックリストのユーザーからの招待を拒否するかどうか。 true か false
blacklist-autoblock       : ブラックリストのユーザーをブロックするかの設定。 true か false
blacklist-autokick        : ブラックリストのユーザーを自動的にパーティーからキックするかの設定。 true か false
blacklist-autochatban     : ブラックリストのユーザーを自動的にチャットバンするかどうか。 true か false
blacklist-ignorecommand   : ブラックリストのユーザーからのコマンドを無視するかどうか。 true か false
whitelist                 : ホワイトリストに指定するユーザーのリスト。 ユーザー名かユーザーID
whitelist-allowinvite     : ホワイトリストのユーザーがボットをいつでも招待できるようにするかの設定。 true か false
whitelist-declineinvite   : ホワイトリストのユーザーがパーティーにいるとき、招待を拒否するかどうか。 true か false
whitelist-ignorelock      : ホワイトリストのユーザーがスキンロック等を無視できるかどうか。 true か false
whitelist-ownercommand    : ホワイトリストのユーザーが所有者コマンドを使えるかどうか。 true か false
whitelist-ignoreng        : ホワイトリストのユーザーがNGワードを無視できるかどうか。 true か false
invitelist                : inviteallコマンドで招待するユーザーのリスト
otherbotlist              : ignorebotで無視する他のボット

Discord
enabled                   : Discord Botを起動するかどうか true か false
token                     : Discord Botのトークン
owner                     : 所有者のユーザーID
channels                  : ボットのコマンドチャンネルとして使用するチャンネルのチャンネル名 後述
status                    : Discord Botのステータス。 変数が使えます。 後述
status_type               : Discord Botのステータスの種類。 後述
discord                   : ボットがDiscordからコマンドを受け付けるかどうか。 true か false
disablediscordperfectly   : Discordが無効の場合、所有者も使えなくするかどうか
blacklist                 : ブラックリストに指定するユーザーのリスト ユーザーID
blacklist-ignorecommand   : ブラックリストのユーザーからのコマンドを無視するかどうか。 true か false
whitelist                 : ホワイトリストに指定するユーザーのリスト ユーザーID
whitelist-ignorelock      : ホワイトリストのユーザーがスキンロック等を無視できるかどうか。 true か false
whitelist-ownercommand    : ホワイトリストのユーザーが所有者コマンドを使えるかどうか。 true か false
whitelist-ignoreng        : ホワイトリストのユーザーがNGワードを無視できるかどうか。 true か false

Web
enabled                   : ウェブサーバーを起動するかどうか。 true か false
ip                        : ウェブサーバーのIPアドレス 後述
port                      : ウェブサーバーのポート番号
password                  : ウェブサーバーのパスワード
login_required            : ウェブサーバーにアクアスするのにパスワードが必要かどうか。 true か false
web                       : ウェブからのコマンドを受け付けるかどうか。 true か false
log                       : ウェブサーバーのアクセスログを出すかどうか。 true か false

replies-matchmethod       : repliesのマッチ方式。 後述
ng-words                  : NGワードに指定する言葉
ng-word-matchmethod       : NGワードのマッチ方式
ng-word-kick              : NGワードを発言したユーザーをキックするかどうか。 true か false
ng-word-chatban           : NGワードを発言したユーザーをチャットバンするかどうか。 true か false
ng-word-blacklist         : NGワードを発言したユーザーをブラックリストに入れるかどうか。 true か false
lang                      : ボットの言語
search-lang               : アイテム検索に使う言語
restart_in                : ボットが再起動するまでの時間
search_max                : 検索の最大数
no-logs                   : コンソールにログを出すかどうか。 true か false
ingame-error              : プレイヤーにエラーを送信するかどうか。 true か false
discord-log               : Discordにログを送信するかどうか。 true か false
omit-over2000             : Discordのログで2000文字を超過した場合に2000文字以上を切り捨てるかどうか。 true か false
skip-if-overflow          : Discordのログであまりにもログ送信が遅れた場合、溜まったログを削除するかどうか。 true か false
hide-email                : Discordのログでメールアドレスを隠すかどうか。 true か false
hide-token                : Discordのログでトークンを隠すかどうか。 true か false
hide-webhook              : Discordのログでwebhookのurlを隠すかどうか。 true か false
webhook                   : Discordのwebhookのurl
caseinsensitive           : コマンドを大文字小文字、平仮名片仮名を区別しないかどうか。 true か false
loglevel                  : ログにどのくらいの情報を流すか normal か info か debug
debug                     : Fortnitepyのデバッグモードをオンにするかどうか。 true か false
コマンド一覧

ここに書かれているコマンド名は、ただの識別名
全てのコマンドの発動ワードはcommands.json(コマンドエディター)を用いて変更できる
全て , で区切ることで複数設定可
全てのコマンドはデフォルトでは所有者しか使用できない
アイテム名を打つことでそのアイテムにすることもできる

usercommands                              : ユーザーも使えるコマンドを指定する。  ここにあるコマンドに加え["cid_","bid_","petcarrier_","pickaxe_id_","eid_","emoji_","toy_","item-search"]が使用できる
true                                      : コマンドの true として扱う文字列
false                                     : コマンドの false として扱う文字列
me                                        : コマンドの送り主として扱う文字列
prev                                      : 一つ前のコマンドを繰り返す
eval                                      : eval [プログラム] 内容を式として評価し、その内容を返す
exec                                      : exec [プログラム] 内容を文として評価し、その内容を返す
restart                                   : プログラムを再起動する
relogin                                   : アカウントに再ログインする
reload                                    : configとcommandsを再読み込みする
addblacklist                              : addblacklist [ユーザー名/ユーザーID] ユーザーをFortniteのブラックリストに追加する
removeblacklist                           : removeblacklist [ユーザー名/ユーザーID] ユーザーをFortniteのブラックリストから削除する
addwhitelist                              : addwhitelist [ユーザー名/ユーザーID] ユーザーをFortniteのホワイトリストに追加する
removewhitelist                           : removewhitelist [ユーザー名/ユーザーID] ユーザーをFortniteのホワイトリストから削除する
addblacklist_discord                      : addblacklist_discord [ユーザーID] ユーザーをDiscordのブラックリストに追加する
removeblacklist_discord                   : removeblacklist_discord [ユーザーID] ユーザーをDiscordのブラックリストから削除する
addwhitelist_discord                      : addwhitelist_discord [ユーザーID] ユーザーをDiscordのホワイトリストに追加する
removewhitelist_discord                   : removewhitelist_discord [ユーザーID] ユーザーをDiscordのホワイトリストから削除する
addinvitelist                             : addinvitelist [ユーザー名/ユーザーID] ユーザーを招待リストに追加する
removeinvitelist                          : removeinvitelist [ユーザー名/ユーザーID] ユーザーを招待リストから削除する
get                                       : get [ユーザー名/ユーザーID] パーティーにいるユーザーの情報を取得する
friendcount                               : 現在のフレンド数を表示する
pendingcount                              : 現在のフレンド申請数を表示する(方向関係なし)
blockcount                                : 現在のブロック数を表示する
friendlist                                : 現在のフレンドリストを表示する
pendinglist                               : 現在のフレンド申請リストを表示する
blocklist                                 : 現在のブロックリストを表示する
outfitmimic                               : outfitmimic [true / false / ユーザー名/ユーザーID] 他人のスキンを真似るかどうか
backpackmimic                             : backpackmimic [true / false / ユーザー名/ユーザーID] 他人のバッグを真似るかどうか
pickaxemimic                              : pickaxemimic [true / false / ユーザー名/ユーザーID] 他人のツルハシを真似るかどうか
emotemimic                                : emotemimic [true / false / ユーザー名/ユーザーID] 他人のエモートを真似るかどうか
whisper                                   : whisper [true / false] 囁きからのコマンドを受け付けるかどうか
partychat                                 : partychat [true / false] パーティーチャットからのコマンドを受け付けるかどうか
discord                                   : discord [true / false] Discordからのコマンドを受け付けるかどうか
web                                       : web [true / false] ウェブからのコマンドを受け付けるかどうか
disablewhisperperfectly                   : whisperperfect [true / false] 囁きが無効の時、所有者も使えなくするかどうか
disablepartychatperfectly                 : partychatperfect [true / false] パーティーチャットが無効の時、所有者も使えなくするかどうか
disablediscordperfectly                   : discordperfect [true / false] Discordが無効の時、所有者も使えなくするかどうか
acceptinvite                              : acceptinvite [true / false] パーティー招待を承諾するかどうか
acceptfriend                              : acceptfriend [true / false] フレンド申請を承諾するかどうか
joinmessageenable                         : joinmessageenable [true / false] パーティーに誰かが参加した時のメッセージを出すかどうか
randommessageenable                       : randommessageenable [true / false] パーティーに誰かが参加したときのランダムメッセージを出すかどうか
wait                                      : configのwaitintervalの秒数だけ招待を拒否する
join                                      : join [ユーザー名/ユーザーID] ユーザーのパーティーに参加する
joinid                                    : joinid [パーティーID] パーティーに参加する
leave                                     : パーティーを離脱する
invite                                    : invite [ユーザー名 / ユーザーID] ユーザーをパーティーに招待する
inviteall                                 : configのinvitelistのユーザーを招待する
message                                   : message [ユーザー名 / ユーザーID] : [内容] ユーザーにメッセージを送信する
partymessage                              : partymessage [内容] パーティーチャットにメッセージを送信する
sendall                                   : sendall [内容] 全てのボットに同じコマンドを実行する
status                                    : status [内容] ステータスを設定する
banner                                    : banner [バナーID] [バナーの色] バナーを設定する
avatar                                    : avatar [CID] [色(任意)] アバターを設定する
level                                     : level [レベル] レベルを設定する
bp                                        : bp [ティア] [XPブースト] [フレンドXPブースト] バトルパス情報を設定する
privacy                                   : privacy [privacy_public / privacy_friends_allow_friends_of_friends / privacy_friends / privacy_private_allow_friends_of_friends / privacy_private] パーティーのプライバシーを変更する
privacy_public                            : privacy コマンドで使う privacy_public
privacy_friends_allow_friends_of_friends  : privacy コマンドで使う privacy_friends_allow_friends_of_friends
privacy_friends                           : privacy コマンドで使う privacy_friends
privacy_private_allow_friends_of_friends  : privacy コマンドで使う privacy_private_allow_friends_of_friends
privacy_private                           : privacy コマンドで使う privacy_private
getuser                                   : getuser [ユーザー名 / ユーザーID] ユーザーの名前とIDを表示する
getfriend                                 : getefriend [ユーザー名 / ユーザーID] ユーザーの名前とIDを表示する
getpending                                : getpending [ユーザー名 / ユーザーID] ユーザーの名前とIDを表示する
getblock                                  : getblock [ユーザー名 / ユーザーID] ユーザーの名前とIDを表示する
info                                      : info [info_party / info_item / id / skin / bag / pickaxe / emote] パーティー/アイテムの情報を表示する
info_party                                : info コマンドで使う info_party
pending                                   : pending [true / false] 保留しているフレンド申請を全て承諾/拒否する
removepending                             : 自分が送ったフレンド申請を全て解除する
addfriend                                 : addfriend [ユーザー名 / ユーザーID] ユーザーにフレンド申請を送信する
removefriend                              : removefriend [ユーザー名 / ユーザーID] ユーザーをフレンドから削除する
removeallfriend                           : removeallfriend 全てのフレンドを削除する
remove_offline_for                        : remove_offline_for [日] [時間(任意)] [分(任意)] 指定した時間以上オフラインのフレンドを削除する
acceptpending                             : acceptpending [ユーザー名 / ユーザーID] ユーザーからのフレンド申請を承諾する
declinepending                            : declinepending [ユーザー名 / ユーザーID] ユーザーからのフレンド申請を拒否する
blockfriend                               : blockfriend[ユーザー名 / ユーザーID] ユーザーをブロックする
unblockfriend                             : unblockfriend [ユーザー名 / ユーザーID] ユーザーをブロック解除する
voice                                     : voice [true / false] パーティーのボイスチャットを有効にするか。それ以前に参加していたメンバーには効果がありません
chatban                                   : chatban [ユーザー名 / ユーザーID] : [理由(任意)] ユーザーをチャットバンする
promote                                   : promote [ユーザー名 / ユーザーID] ユーザーにパーティーリーダーを譲渡する
kick                                      : kick [ユーザー名 / ユーザーID] ユーザーをキックする
hide                                      : hide [ユーザー名 / ユーザーID(任意)] ユーザーを非表示にする
show                                      : show [ユーザー名 / ユーザーID(任意)] ユーザーを表示する
ready                                     : 準備OK 状態にする
unready                                   : 準備中 状態にする
sitout                                    : 欠場中 状態にする
match                                     : match [人数(任意)] マッチ状態を設定する
unmatch                                   : マッチ状態を解除する
swap                                      : swap [ユーザー名 / ユーザーID] ユーザーと位置を交換する
outfitlock                                : outfitlock [true / false] スキンの変更をするかどうか
backpacklock                              : backpacklock [true / false] バッグの変更をするかどうか
pickaxelock                               : pickaxelock [true / false] ツルハシの変更をするかどうか
emotelock                                 : emotelock [true / false] エモートの変更をするかどうか
stop                                      : エモート/all系コマンドの表示を停止する
addeditems                                : アップデートで追加されたすべてのアイテムを表示する
shopitems                                 : アイテムショップのアイテムをすべて表示する
alloutfit                                 : 全てのコスチュームを表示する
allbackpack                               : 全てのバックアクセサリーを表示する
allpet                                    : 全てのペットを表示する
allpickaxe                                : 全ての収集ツールを表示する
allemote                                  : 全てのエモートを表示する
cid                                       : cid [CID] CIDでアイテムを検索し、見つかったアイテムに設定する
bid                                       : bid [BID] BIDでアイテムを検索し、見つかったアイテムに設定する
petcarrier                                : petcarrier [Petcarrier] Petcarrierでアイテムを検索し、見つかったアイテムに設定する
pickaxe_id                                : pickaxe_id [Pickaxe_ID] Pickaxe_IDでアイテムを検索し、見つかったアイテムに設定する
eid                                       : eid [EID] EIDでアイテムを検索し、見つかったアイテムに設定する
emoji_id                                  : emoji_id [Emoji] Emojiでアイテムを検索し、見つかったアイテムに設定する
toy_id                                    : toy_id [Toy] Toyでアイテムを検索し、見つかったアイテムに設定する
id                                        : id [ID] IDでアイテムを検索し、見つかったアイテムに設定する
outfit                                    : outfit [コスチューム名] コスチューム名でコスチュームを検索し、見つかったアイテムに設定する
backpack                                  : backpack [バックアクセサリー名] バックアクセサリー名でバックアクセサリーを検索し、見つかったアイテムに設定する
pet                                       : pet [ペット名] ペット名でペットを検索し、見つかったアイテムに設定する
pickaxe                                   : pickaxe [収集ツール名] 収集ツール名で収集ツールを検索し、見つかったアイテムに設定する
emote                                     : emote [エモート名] エモート名でエモートを検索し、見つかったアイテムに設定する
emoji                                     : emoji [エモートアイコン名] エモートアイコン名でエモートアイコンを検索し、見つかったアイテムに設定する
toy                                       : toy [おもちゃ名] おもちゃ名でおもちゃを検索し、見つかったアイテムに設定する
item                                      : item [アイテム名] アイテム名でアイテムを検索し、見つかったアイテムに設定する
set                                       : set [セット名] セット名でアイテムを検索し、見つかったアイテムに設定する
setvariant                                : setvariant [skin / bag / pickaxe] [variant] [数値] variant/数値は無限に設定可 数が合わない場合は無視される。スタイル情報を設定する。後述
addvariant                                : addvariant [skin / bag / pickaxe] [variant] [数値] variant/数値は無限に設定可 数が合わない場合は無視される。現在のスタイル情報にスタイル情報を追加する。後述
setstyle                                  : setstyle [skin / bag / pickaxe] 現在付けているアイテムのスタイルを検索し、そのスタイルに設定する
addstyle                                  : addstyle [skin / bag / pickaxe] 現在付けているアイテムのスタイルを検索し、そのスタイルに現在のスタイルを追加する
setenlightenment                          : setenlightenment [数値] [数値] enlightenment情報を設定する 後述
outfitasset                               : outfitasset [アセットパス] スキンをアセットパスから設定する
backpackasset                             : backpackasset [アセットパス] バッグをアセットパスから設定する
pickasset                                 : pickasset [アセットパス] ツルハシをアセットパスから設定する
emoteasset                                : emoteasset [アセットパス] エモートをアセットパスから設定する
