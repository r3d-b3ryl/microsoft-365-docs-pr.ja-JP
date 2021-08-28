---
title: Microsoft Defender for Endpoint (Linux) でスキャンをスケジュールする方法
description: 組織の資産をよりよく保護するために、Microsoft Defender for Endpoint (Linux) の自動スキャン時間をスケジュールする方法について説明します。
keywords: microsoft、 defender、 Microsoft Defender for Endpoint, Linux, スキャン, ウイルス対策, microsoft Defender for endpoint (linux)
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
ms.openlocfilehash: d1f6f004738dc50238b0941f7c7182400117fb50
ms.sourcegitcommit: c2d752718aedf958db6b403cc12b972ed1215c00
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58559012"
---
# <a name="schedule-scans-with-microsoft-defender-for-endpoint-linux"></a>Microsoft Defender for Endpoint (Linux) でのスキャンのスケジュール設定

Linux のスキャンを実行するには、「サポートされている [コマンド」を参照してください](/microsoft-365/security/defender-endpoint/linux-resources#supported-commands)。

Linux (および Unix) には、スケジュールされたタスクを実行できる **crontab** (タスク スケジューラと同様) というツールがあります。

## <a name="pre-requisite"></a>前提条件

> [!NOTE]
> すべてのタイム ゾーンの一覧を取得するには、次のコマンドを実行します。 `timedatectl list-timezones`<br>
> タイム ゾーンの例:
>
> - `America/Los_Angeles`
> - `America/New_York`
> - `America/Chicago`
> - `America/Denver`

## <a name="to-set-the-cron-job"></a>Cron ジョブを設定するには

次のコマンドを使用します。

### <a name="backup-crontab-entries"></a>crontab エントリのバックアップ

```bash
sudo crontab -l > /var/tmp/cron_backup_200919.dat
```

> [!NOTE]
> ここで、200919 == YRMMDD

> [!TIP]
> 編集または削除する前に、この操作を行います。

crontab を編集し、新しいジョブをルート ユーザーとして追加するには、次の方法を実行します。

```bash
sudo crontab -e
```

> [!NOTE]
> 既定のエディターは VIM です。

次の情報が表示される場合があります。

```outbou
0 * * * * /etc/opt/microsoft/mdatp/logrorate.sh
```

"Insert" を押す

次のエントリを追加します。

```bash
CRON_TZ=America/Los_Angeles

0 2 * * sat /bin/mdatp scan quick > ~/mdatp_cron_job.log
```

> [!NOTE]
> この例では、00 分、2 時に設定しています。 (24 時間形式の時間)、月の任意の日、任意の月、土曜日。 つまり、土曜日は 2:00 に実行されます。 太平洋 (UTC -8)。

"Esc" を押す

二重引用符 `:wq` を付けずに""と入力します。

> [!NOTE]
> w == 書き込み、q == quit

cron ジョブを表示するには、 `sudo crontab -l`

:::image type="content" source="../../media/linux-mdatp-1.png" alt-text="linux mdatp。":::

#### <a name="to-inspect-cron-job-runs"></a>cron ジョブの実行を調するには

```bash
sudo grep mdatp /var/log/cron
```

#### <a name="to-inspect-the-mdatp_cron_joblog"></a>mdatp_cron_job.log* を検査するには

```bash
sudo nano mdatp_cron_job.log
```

## <a name="for-those-who-use-ansible-chef-or-puppet"></a>Ansible、Chef、または Puppet を使用するユーザー向け

次のコマンドを使用します。

### <a name="to-set-cron-jobs-in-ansible"></a>Ansible で cron ジョブを設定するには

```bash
cron - Manage cron.d and crontab entries

See [https://docs.ansible.com/ansible/latest/modules/cron_module.html](https://docs.ansible.com/ansible/latest/modules/cron_module.html) for more information.

### To set crontabs in Chef

```bash
cron resource
```bash

```
詳細については、「<https://docs.chef.io/resources/cron/>」を参照してください。

### <a name="to-set-cron-jobs-in-puppet"></a>Puppet で cron ジョブを設定するには

```bash
Resource Type: cron
```

詳細については、「<https://puppet.com/docs/puppet/5.5/types/cron.html>」を参照してください。

Puppet による自動化: Cron ジョブとスケジュールされたタスク

詳細については、「[https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/](https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/)」を参照してください。

## <a name="additional-information"></a>ページの先頭へ

### <a name="to-get-help-with-crontab"></a>crontab のヘルプを表示するには

```bash
man crontab
```

### <a name="to-get-a-list-of-crontab-file-of-the-current-user"></a>現在のユーザーの crontab ファイルの一覧を取得するには

```bash
crontab -l
```

### <a name="to-get-a-list-of-crontab-file-of-another-user"></a>別のユーザーの crontab ファイルの一覧を取得するには

```bash
crontab -u username -l
```

### <a name="to-backup-crontab-entries"></a>crontab エントリをバックアップするには

```bash
crontab -l > /var/tmp/cron_backup.dat
```

> [!TIP]
> 編集または削除する前に、この操作を行います。

### <a name="to-restore-crontab-entries"></a>crontab エントリを復元するには

```bash
crontab /var/tmp/cron_backup.dat
```

### <a name="to-edit-the-crontab-and-add-a-new-job-as-a-root-user"></a>crontab を編集し、新しいジョブをルート ユーザーとして追加するには

```bash
sudo crontab -e
```

### <a name="to-edit-the-crontab-and-add-a-new-job"></a>crontab を編集して新しいジョブを追加するには

```bash
crontab -e
```

### <a name="to-edit-other-users-crontab-entries"></a>他のユーザーの crontab エントリを編集するには

```bash
crontab -u username -e
```

### <a name="to-remove-all-crontab-entries"></a>すべての crontab エントリを削除するには

```bash
crontab -r
```

### <a name="to-remove-other-users-crontab-entries"></a>他のユーザーの crontab エントリを削除するには

```bash
crontab -u username -r
```

### <a name="explanation"></a>説明

+—————- 分 (値: 0 ~ 59) (特殊文字: 、 - * /)  <br>
|+————-時間 (値: 0 ~ 23) (特殊文字: 、 - * /) <br>
| |+———-日 (値: 1 ~ 31) (特殊文字: 、 - * / L W C)  <br>
| | |+——-月 (値: 1 ~ 12) (特殊文字: ,- * / )  <br>
| | | |+-- 日 (値: 0 ~ 6) (日曜=0 または 7) (特殊文字: , - * / L W C) <br>
| | | | |*****コマンドを実行する
