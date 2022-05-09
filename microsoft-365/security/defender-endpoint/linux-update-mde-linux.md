---
title: Microsoft Defender for Endpointの更新をスケジュールする方法 (Linux)
description: 組織の資産をより適切に保護するために、Microsoft Defender for Endpoint (Linux) の更新をスケジュールする方法について説明します。
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
ms.openlocfilehash: 6fb3141b33948c5c452096c83a2f02657c199575
ms.sourcegitcommit: 2697938d2d4fec523b501c5e7b0b8ec8f34e59b0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2022
ms.locfileid: "63450550"
---
# <a name="schedule-an-update-of-the-microsoft-defender-for-endpoint-linux"></a>Microsoft Defender for Endpoint (Linux) の更新をスケジュールする

**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

Linux 上のMicrosoft Defender for Endpointで更新プログラムを実行するには、「Microsoft Defender for Endpoint [用の更新プログラムを Linux にデプロイする](/microsoft-365/security/defender-endpoint/linux-updates)」を参照してください。

Linux (および Unix) には、スケジュールされたタスクを実行できるように **crontab** (タスク スケジューラと同様) というツールがあります。

## <a name="pre-requisite"></a>前提条件

> [!NOTE]
> すべてのタイム ゾーンの一覧を取得するには、次のコマンドを実行します。 `timedatectl list-timezones`
>
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
sudo crontab -l > /var/tmp/cron_backup_201118.dat
```

> [!NOTE]
> ここで201118 == YYMMDD

> [!TIP]
> 編集または削除する前に、この操作を行います。

crontab を編集し、ルート ユーザーとして新しいジョブを追加するには、

```bash
sudo crontab -e
```

> [!NOTE]
> 既定のエディターは VIM です。

次が表示される場合があります。

```output
0****/etc/opt/microsoft/mdatp/logrorate.sh
```

And

```output
02**sat /bin/mdatp scan quick>~/mdatp_cron_job.log
```

[Microsoft Defender for Endpointを使用したスキャンのスケジュール (Linux)](linux-schedule-scan-mde.md) に関する記事を参照してください

"Insert" キーを押します

次のエントリを追加します。

```bash
CRON_TZ=America/Los_Angeles
```

> #<a name="rhel-and-variants-centos-and-oracle-linux"></a>!RHEL とバリアント (CentOS および Oracle Linux)
>
> ```bash
> 0 6 * * sun [ $(date +%d) -le 15 ] && sudo yum update mdatp -y >> ~/mdatp_cron_job.log
> ```

> #<a name="sles-and-variants"></a>!SLES とバリアント
>
> ```bash
> 0 6 * * sun [ $(date +%d) -le 15 ] && sudo zypper update mdatp >> ~/mdatp_cron_job.log
> ```

> #<a name="ubuntu-and-debian-systems"></a>!Ubuntu および Debian システム
>
> ```bash
> 0 6 * * sun [ $(date +%d) -le 15 ] && sudo apt-get install --only-upgrade mdatp >> ~/mdatp_cron_job.log
> ```

> [!NOTE]
> 上の例では、00 分、午前 6 時 (24 時間形式の時間)、月の任意の日、任意の月、日曜日に設定しています。[$(date +\%d) -le 15] == 15 日 (第 3 週) 以下でない限り、実行されません。 つまり、月の第 3 日曜日 (7) ごとに午前 6 時に実行されます。 太平洋 (UTC -8)。

"Esc" キーを押します

二重引用符を付け、"`:wq`" と入力します。

> [!NOTE]
> w == write、q == quit

cron ジョブを表示するには、「」と入力します。 `sudo crontab -l`

:::image type="content" source="images/update-MDE-linux-4634577.jpg" alt-text="Linux 上の Defender for Endpoint を更新します。":::

cron ジョブの実行を調べるには:

```bash
sudo grep mdatp /var/log/cron
```

mdatp_cron_job.log を調べるには

```bash
sudo nano mdatp_cron_job.log
```

## <a name="for-those-who-use-ansible-chef-or-puppet"></a>Ansible、Chef、Puppet を使用するユーザー向け

次のコマンドを使用します。

### <a name="to-set-cron-jobs-in-ansible"></a>Ansible で cron ジョブを設定するには

```bash
cron - Manage cron.d and crontab entries
```

詳細については、「<https://docs.ansible.com/ansible/latest/modules/cron_module.html>」を参照してください。

### <a name="to-set-crontabs-in-chef"></a>Chef で crontabs を設定するには

```bash
cron resource
```

詳細については、「<https://docs.chef.io/resources/cron/>」を参照してください。

### <a name="to-set-cron-jobs-in-puppet"></a>Puppet で cron ジョブを設定するには

リソースの種類: cron

詳細については、「<https://puppet.com/docs/puppet/5.5/types/cron.html>」を参照してください。

Puppet を使用した自動化: Cron ジョブとスケジュールされたタスク

詳細については、「<https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/>」を参照してください。

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

<pre>
+—————- minute (values: 0 - 59) (special characters: , - * /)  <br>
| +————- hour (values: 0 - 23) (special characters: , - * /) <br>
| | +———- day of month (values: 1 - 31) (special characters: , - * / L W C)  <br>
| | | +——- month (values: 1 - 12) (special characters: ,- * / )  <br>
| | | | +—- day of week (values: 0 - 6) (Sunday=0 or 7) (special characters: , - * / L W C) <br>
| | | | |*****command to be executed
</pre>
