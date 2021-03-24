---
title: Microsoft Defender for Endpoint (Linux) でスキャンをスケジュールする方法
description: 組織の資産をよりよく保護するために、Microsoft Defender for Endpoint (Linux) の自動スキャン時間をスケジュールする方法について説明します。
keywords: microsoft、Defender、atp、Linux、スキャン、ウイルス対策、エンドポイント用 microsoft Defender (Linux)
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: d3f5d4c490e28c7985a0420fa5013a8e0f51a167
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51065723"
---
# <a name="schedule-scans-with-microsoft-defender-for-endpoint-linux"></a>Microsoft Defender for Endpoint (Linux) でのスキャンのスケジュール設定

Linux のスキャンを実行するには、「サポートされている [コマンド」を参照してください](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/linux-resources#supported-commands)。

Linux (および Unix) には、スケジュールされたタスクを実行できる **crontab** (タスク スケジューラと同様) というツールがあります。

## <a name="pre-requisite"></a>前提条件

> [!NOTE]
> すべてのタイム ゾーンの一覧を取得するには、次のコマンドを実行します。 `timedatectl list-timezones`<br>
> タイム ゾーンの例:
> - `America/Los_Angeles`
> - `America/New_York`
> - `America/Chicago`
> - `America/Denver`

## <a name="to-set-the-cron-job"></a>Cron ジョブを設定するには
次のコマンドを使用します。

**crontab エントリをバックアップするには**

`sudo crontab -l > /var/tmp/cron_backup_200919.dat`

> [!NOTE]
> Where 200919 == YRMMDD

> [!TIP]
> 編集または削除する前に、この操作を行います。 <br>

crontab を編集し、新しいジョブをルート ユーザーとして追加するには、次の方法を実行します。 <br>
`sudo crontab -e`

> [!NOTE]
> 既定のエディターは VIM です。

次の情報が表示される場合があります。

0 * * * * * /etc/opt/microsoft/mdatp/logrorate.sh

"Insert" を押す

次のエントリを追加します。

CRON_TZ=America/Los_Angeles

0 2 * sat /bin/mdatp スキャン クイック > ~/mdatp_cron_job.log

> [!NOTE]
>この例では、00 分、2 時に設定しています。 (24 時間形式の時間)、月の任意の日、任意の月、土曜日。 つまり、土曜日は 2:00 に実行されます。 太平洋 (UTC –8)。

"Esc" を押す

二重引用符を付けずに":wq" と入力します。

> [!NOTE]
> w == 書き込み、q == quit

cron ジョブを表示するには、 `sudo crontab -l`

:::image type="content" source="/microsoft-365/security/defender-endpoint/images/linux-mdatp-1" alt-text="linux mdatp":::

**cron ジョブの実行を調するには**

`sudo grep mdatp /var/log/cron`

**mdatp_cron_job.log を調するには**

`sudo nano mdatp_cron_job.log`

## <a name="for-those-who-use-ansible-chef-or-puppet"></a>Ansible、Chef、または Puppet を使用するユーザー向け

次のコマンドを使用します。
### <a name="to-set-cron-jobs-in-ansible"></a>Ansible で cron ジョブを設定するには

`cron – Manage cron.d and crontab entries`

詳細については、「[https://docs.ansible.com/ansible/latest/modules/cron_module.html](https://docs.ansible.com/ansible/latest/modules/cron_module.html)」を参照してください。

### <a name="to-set-crontabs-in-chef"></a>Chef で crontabs を設定するには
`cron resource`

詳細については、「[https://docs.chef.io/resources/cron/](https://docs.chef.io/resources/cron/)」を参照してください。

### <a name="to-set-cron-jobs-in-puppet"></a>Puppet で cron ジョブを設定するには
リソースの種類: cron

詳細については、「[https://puppet.com/docs/puppet/5.5/types/cron.html](https://puppet.com/docs/puppet/5.5/types/cron.html)」を参照してください。

Puppet による自動化: Cron ジョブとスケジュールされたタスク

詳細については、「[https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/](https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/)」を参照してください。

## <a name="additional-information"></a>ページの先頭へ

**crontab のヘルプを表示するには**

`man crontab`

**現在のユーザーの crontab ファイルの一覧を取得するには**

`crontab -l`

**別のユーザーの crontab ファイルの一覧を取得するには**

`crontab -u username -l`

**crontab エントリをバックアップするには**

`crontab -l > /var/tmp/cron_backup.dat`

> [!TIP]
> 編集または削除する前に、この操作を行います。 <br>

**crontab エントリを復元するには**

`crontab /var/tmp/cron_backup.dat`

**crontab を編集し、新しいジョブをルート ユーザーとして追加するには**

`sudo crontab -e`

**crontab を編集して新しいジョブを追加するには**

`crontab -e`

**他のユーザーの crontab エントリを編集するには**

`crontab -u username -e`

**すべての crontab エントリを削除するには**

`crontab -r`

**他のユーザーの crontab エントリを削除するには**

`crontab -u username -r`

**説明**

+—————- 分 (値: 0 ~ 59) (特殊文字: 、 – * /)  <br>
|+————-時間 (値: 0 ~ 23) (特殊文字: 、 – * /) <br>
| |+———-日 (値: 1 ~ 31) (特殊文字: , – * / L W C)  <br>
| | |+——-月 (値: 1 ~ 12) (特殊文字: ,- * / )  <br>
| | | |+—- 日 (値: 0 ~ 6) (日曜日=0 または 7) (特殊文字: , – * / L W C) <br>
| | | | |*****コマンドを実行する


