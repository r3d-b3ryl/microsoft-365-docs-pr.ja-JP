---
title: Microsoft Defender for Endpoint (Linux) を使用してスキャンをスケジュールする方法
description: 組織の資産をより適切に保護するために、Microsoft Defender for Endpoint (Linux) の自動スキャン時間をスケジュールする方法について説明します。
keywords: microsoft, defender, Microsoft Defender for Endpoint, Linux, スキャン, ウイルス対策, Microsoft Defender for endpoint (linux)
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 706284ed0adf49c4da6357b6bb8217d5a14268e1
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/06/2022
ms.locfileid: "64663492"
---
# <a name="schedule-scans-with-microsoft-defender-for-endpoint-linux"></a>Microsoft Defender for Endpoint (Linux) を使用してスキャンをスケジュールする

**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)


Linux のスキャンを実行するには、「 [サポートされているコマンド」を](/microsoft-365/security/defender-endpoint/linux-resources#supported-commands)参照してください。

Linux (および Unix) には、スケジュールされたタスクを実行できるように **crontab** (タスク スケジューラと同様) というツールがあります。

## <a name="pre-requisite"></a>前提条件

> [!NOTE]
> すべてのタイム ゾーンの一覧を取得するには、次のコマンドを実行します。 `timedatectl list-timezones`<br>
> タイムゾーンの例:
>
> - `America/Los_Angeles`
> - `America/New_York`
> - `America/Chicago`
> - `America/Denver`

## <a name="to-set-the-cron-job"></a>Cron ジョブを設定するには

次のコマンドを使用します。

### <a name="backup-crontab-entries"></a>crontab エントリをバックアップする

```bash
sudo crontab -l > /var/tmp/cron_backup_200919.dat
```

> [!NOTE]
> ここで200919 == YRMMDD

> [!TIP]
> 編集または削除する前に、この操作を行います。

crontab を編集し、ルート ユーザーとして新しいジョブを追加するには、

```bash
sudo crontab -e
```

> [!NOTE]
> 既定のエディターは VIM です。

次が表示される場合があります。

```outbou
0 * * * * /etc/opt/microsoft/mdatp/logrorate.sh
```

"Insert" キーを押します

次のエントリを追加します。

```bash
CRON_TZ=America/Los_Angeles

0 2 * * sat /bin/mdatp scan quick > ~/mdatp_cron_job.log
```

> [!NOTE]
> この例では、午前 00 分、午前 2 時に設定しています。 (24 時間形式の時間)、月の任意の日、任意の月、土曜日。 つまり、土曜日は午前 2 時に実行されます。 太平洋 (UTC -8)。

"Esc" キーを押します

二重引用符を含まない "`:wq`" と入力します。

> [!NOTE]
> w == write、q == quit

cron ジョブを表示するには、「」と入力します。 `sudo crontab -l`

:::image type="content" source="../../media/linux-mdatp-1.png" alt-text="Linux mdatp ページ" lightbox="../../media/linux-mdatp-1.png":::

#### <a name="to-inspect-cron-job-runs"></a>cron ジョブの実行を調べるには

```bash
sudo grep mdatp /var/log/cron
```

#### <a name="to-inspect-the-mdatp_cron_joblog"></a>mdatp_cron_job.log* を調べるには

```bash
sudo nano mdatp_cron_job.log
```

## <a name="for-those-who-use-ansible-chef-or-puppet"></a>Ansible、Chef、Puppet を使用するユーザー向け

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

Puppet を使用した自動化: Cron ジョブとスケジュールされたタスク

詳細については、「[https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/](https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/)」を参照してください。

## <a name="additional-information"></a>その他の情報

### <a name="to-get-help-with-crontab"></a>crontab に関するヘルプを表示するには

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

### <a name="to-edit-the-crontab-and-add-a-new-job-as-a-root-user"></a>crontab を編集し、ルート ユーザーとして新しいジョブを追加するには

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

+—————-分 (値: 0 ~ 59) (特殊文字: , \- \* /)  <br>
|+————-時間 (値: 0 ~ 23) (特殊文字: , \- \* /) <br>
| |+———-日 (値: 1 ~ 31) (特殊文字: , \- \* / L W C)  <br>
| | |+——-月 (値: 1 ~ 12) (特殊文字: , \- \* / )  <br>
| | | |+—- 曜日 (値: 0 ~ 6) (日曜日=0 または 7) (特殊文字: , \- \* / L W C) <br>
実行する| | | | |*****コマンド
