---
title: Microsoft Defender for Endpoint (Linux) の更新プログラムをスケジュールする方法
description: 組織の資産を保護するために Microsoft Defender for Endpoint (Linux) の更新プログラムをスケジュールする方法について説明します。
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
ms.openlocfilehash: a967333a58f74938ea70e32e0c48d2decb597e98
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2021
ms.locfileid: "51688803"
---
# <a name="schedule-an-update-of-the-microsoft-defender-for-endpoint-linux"></a><span data-ttu-id="14d16-104">Microsoft Defender for Endpoint (Linux) の更新をスケジュールする</span><span class="sxs-lookup"><span data-stu-id="14d16-104">Schedule an update of the Microsoft Defender for Endpoint (Linux)</span></span>

<span data-ttu-id="14d16-105">Microsoft Defender for Endpoint on Linux で更新プログラムを実行するには [、「Deploy updates for Endpoint on Linux」を参照してください](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/linux-updates)。</span><span class="sxs-lookup"><span data-stu-id="14d16-105">To run an update on Microsoft Defender for Endpoint on Linux, see [Deploy updates for Microsoft Defender for Endpoint on Linux](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/linux-updates).</span></span>

<span data-ttu-id="14d16-106">Linux (および Unix) には、スケジュールされたタスクを実行できる **crontab** (タスク スケジューラと同様) というツールがあります。</span><span class="sxs-lookup"><span data-stu-id="14d16-106">Linux (and Unix) have a tool called **crontab** (similar to Task Scheduler) to be able to run scheduled tasks.</span></span>

## <a name="pre-requisite"></a><span data-ttu-id="14d16-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="14d16-107">Pre-requisite</span></span>

> [!NOTE]
> <span data-ttu-id="14d16-108">すべてのタイム ゾーンの一覧を取得するには、次のコマンドを実行します。 `timedatectl list-timezones`</span><span class="sxs-lookup"><span data-stu-id="14d16-108">To get a list of all the time zones, run the following command: `timedatectl list-timezones`</span></span><br>
> <span data-ttu-id="14d16-109">タイム ゾーンの例:</span><span class="sxs-lookup"><span data-stu-id="14d16-109">Examples for timezones:</span></span> <br>
> - `America/Los_Angeles`
> - `America/New_York`
> - `America/Chicago`
> - `America/Denver`

## <a name="to-set-the-cron-job"></a><span data-ttu-id="14d16-110">Cron ジョブを設定するには</span><span class="sxs-lookup"><span data-stu-id="14d16-110">To set the Cron job</span></span>
<span data-ttu-id="14d16-111">次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="14d16-111">Use the following commands:</span></span>

<span data-ttu-id="14d16-112">**crontab エントリをバックアップするには**</span><span class="sxs-lookup"><span data-stu-id="14d16-112">**To backup crontab entries**</span></span>

`sudo crontab -l > /var/tmp/cron_backup_201118.dat`

> [!NOTE]
> <span data-ttu-id="14d16-113">Where 201118 == YYMMDD</span><span class="sxs-lookup"><span data-stu-id="14d16-113">Where 201118 == YYMMDD</span></span>

> [!TIP]
> <span data-ttu-id="14d16-114">編集または削除する前に、この操作を行います。</span><span class="sxs-lookup"><span data-stu-id="14d16-114">Do this before you edit or remove.</span></span> <br>

<span data-ttu-id="14d16-115">crontab を編集し、新しいジョブをルート ユーザーとして追加するには、次の方法を実行します。</span><span class="sxs-lookup"><span data-stu-id="14d16-115">To edit the crontab, and add a new job as a root user:</span></span> <br>
`sudo crontab -e`

> [!NOTE]
> <span data-ttu-id="14d16-116">既定のエディターは VIM です。</span><span class="sxs-lookup"><span data-stu-id="14d16-116">The default editor is VIM.</span></span>

<span data-ttu-id="14d16-117">次の情報が表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="14d16-117">You might see:</span></span>

<span data-ttu-id="14d16-118">0\*\*\*\*/etc/opt/microsoft/mdatp/logrorate.sh</span><span class="sxs-lookup"><span data-stu-id="14d16-118">0\*\*\*\*/etc/opt/microsoft/mdatp/logrorate.sh</span></span>

<span data-ttu-id="14d16-119">And</span><span class="sxs-lookup"><span data-stu-id="14d16-119">And</span></span>

<span data-ttu-id="14d16-120">02\*\*sat /bin/mdatp スキャンクイック>~/mdatp_cron_job.log</span><span class="sxs-lookup"><span data-stu-id="14d16-120">02\*\*sat /bin/mdatp scan quick>~/mdatp_cron_job.log</span></span>

<span data-ttu-id="14d16-121">「Microsoft [Defender for Endpoint (Linux) でのスキャンのスケジュール設定」を参照してください。](linux-schedule-scan-atp.md)</span><span class="sxs-lookup"><span data-stu-id="14d16-121">See [Schedule scans with Microsoft Defender for Endpoint (Linux)](linux-schedule-scan-atp.md)</span></span>

<span data-ttu-id="14d16-122">"Insert" を押す</span><span class="sxs-lookup"><span data-stu-id="14d16-122">Press “Insert”</span></span>

<span data-ttu-id="14d16-123">次のエントリを追加します。</span><span class="sxs-lookup"><span data-stu-id="14d16-123">Add the following entries:</span></span>

<span data-ttu-id="14d16-124">CRON_TZ=America/Los_Angeles</span><span class="sxs-lookup"><span data-stu-id="14d16-124">CRON_TZ=America/Los_Angeles</span></span>

> #<a name="rhel-and-variants-centos-and-oracle-linux"></a><span data-ttu-id="14d16-125">!RHEL とバリアント (CentOS および Oracle Linux)</span><span class="sxs-lookup"><span data-stu-id="14d16-125">!RHEL and variants (CentOS and Oracle Linux)</span></span>

`06**sun[$(date +\%d) -le 15] sudo yum update mdatp>>~/mdatp_cron_job.log`

> #<a name="sles-and-variants"></a><span data-ttu-id="14d16-126">!SLES とバリアント</span><span class="sxs-lookup"><span data-stu-id="14d16-126">!SLES and variants</span></span>

`06**sun[$(date +\%d) -le 15] sudo zypper update mdatp>>~/mdatp_cron_job.log`

> #<a name="ubuntu-and-debian-systems"></a><span data-ttu-id="14d16-127">!Ubuntu システムと Debian システム</span><span class="sxs-lookup"><span data-stu-id="14d16-127">!Ubuntu and Debian systems</span></span>

`06**sun [$(date +\%d) -le 15] sudo apt-get install --only-upgrade mdatp>>~/mdatp_cron_job.log`

> [!NOTE]
> <span data-ttu-id="14d16-128">上記の例では、00 分、24 時間形式の 6.m.(hour)、月の任意の日、任意の月、日曜日に設定しています。[$(date + \% d) -le 15] == 15 日 (3 週目) 以下の場合は実行されません。</span><span class="sxs-lookup"><span data-stu-id="14d16-128">In the examples above, we are setting it to 00 minutes, 6 a.m.(hour in 24 hour format), any day of the month, any month, on Sundays.[$(date +\%d) -le 15] == Won’t run unless it’s equal or less than the 15th day (3rd week).</span></span> <span data-ttu-id="14d16-129">つまり、月の第 3 日曜日(7) ごとに 6:00 に実行されます。</span><span class="sxs-lookup"><span data-stu-id="14d16-129">Meaning it will run every 3rd Sundays(7) of the month at 6:00 a.m.</span></span> <span data-ttu-id="14d16-130">太平洋 (UTC -8)。</span><span class="sxs-lookup"><span data-stu-id="14d16-130">Pacific (UTC -8).</span></span>

<span data-ttu-id="14d16-131">"Esc" を押す</span><span class="sxs-lookup"><span data-stu-id="14d16-131">Press “Esc”</span></span>

<span data-ttu-id="14d16-132">二重引用符を付け、":wq" と入力します。</span><span class="sxs-lookup"><span data-stu-id="14d16-132">Type “:wq” w/o the double quotes.</span></span>

> [!NOTE]
> <span data-ttu-id="14d16-133">w == 書き込み、q == quit</span><span class="sxs-lookup"><span data-stu-id="14d16-133">w == write, q == quit</span></span>

<span data-ttu-id="14d16-134">cron ジョブを表示するには、 `sudo crontab -l`</span><span class="sxs-lookup"><span data-stu-id="14d16-134">To view your cron jobs, type `sudo crontab -l`</span></span>

:::image type="content" source="images/update-MDE-linux-4634577.jpg" alt-text="MDE Linux の更新":::

<span data-ttu-id="14d16-136">cron ジョブの実行を検査するには、次のコマンドを実行します。 `sudo grep mdatp /var/log/cron`</span><span class="sxs-lookup"><span data-stu-id="14d16-136">To inspect cron job runs: `sudo grep mdatp /var/log/cron`</span></span>

<span data-ttu-id="14d16-137">mdatp_cron_job.log を調するには `sudo nano mdatp_cron_job.log`</span><span class="sxs-lookup"><span data-stu-id="14d16-137">To inspect the mdatp_cron_job.log `sudo nano mdatp_cron_job.log`</span></span>

## <a name="for-those-who-use-ansible-chef-or-puppet"></a><span data-ttu-id="14d16-138">Ansible、Chef、または Puppet を使用するユーザー向け</span><span class="sxs-lookup"><span data-stu-id="14d16-138">For those who use Ansible, Chef, or Puppet</span></span>

<span data-ttu-id="14d16-139">次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="14d16-139">Use the following commands:</span></span>
### <a name="to-set-cron-jobs-in-ansible"></a><span data-ttu-id="14d16-140">Ansible で cron ジョブを設定するには</span><span class="sxs-lookup"><span data-stu-id="14d16-140">To set cron jobs in Ansible</span></span>

`cron – Manage cron.d and crontab entries`

<span data-ttu-id="14d16-141">詳細については、「[https://docs.ansible.com/ansible/latest/modules/cron_module.html](https://docs.ansible.com/ansible/latest/modules/cron_module.html)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="14d16-141">See [https://docs.ansible.com/ansible/latest/modules/cron_module.html](https://docs.ansible.com/ansible/latest/modules/cron_module.html) for more information.</span></span>

### <a name="to-set-crontabs-in-chef"></a><span data-ttu-id="14d16-142">Chef で crontabs を設定するには</span><span class="sxs-lookup"><span data-stu-id="14d16-142">To set crontabs in Chef</span></span>
`cron resource`

<span data-ttu-id="14d16-143">詳細については、「[https://docs.chef.io/resources/cron/](https://docs.chef.io/resources/cron/)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="14d16-143">See [https://docs.chef.io/resources/cron/](https://docs.chef.io/resources/cron/) for more information.</span></span>

### <a name="to-set-cron-jobs-in-puppet"></a><span data-ttu-id="14d16-144">Puppet で cron ジョブを設定するには</span><span class="sxs-lookup"><span data-stu-id="14d16-144">To set cron jobs in Puppet</span></span>
<span data-ttu-id="14d16-145">リソースの種類: cron</span><span class="sxs-lookup"><span data-stu-id="14d16-145">Resource Type: cron</span></span>

<span data-ttu-id="14d16-146">詳細については、「[https://puppet.com/docs/puppet/5.5/types/cron.html](https://puppet.com/docs/puppet/5.5/types/cron.html)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="14d16-146">See [https://puppet.com/docs/puppet/5.5/types/cron.html](https://puppet.com/docs/puppet/5.5/types/cron.html) for more information.</span></span>

<span data-ttu-id="14d16-147">Puppet による自動化: Cron ジョブとスケジュールされたタスク</span><span class="sxs-lookup"><span data-stu-id="14d16-147">Automating with Puppet: Cron jobs and scheduled tasks</span></span>

<span data-ttu-id="14d16-148">詳細については、「[https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/](https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="14d16-148">See [https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/](https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/) for more information.</span></span>

## <a name="additional-information"></a><span data-ttu-id="14d16-149">追加情報</span><span class="sxs-lookup"><span data-stu-id="14d16-149">Additional information</span></span>

<span data-ttu-id="14d16-150">**crontab のヘルプを表示するには**</span><span class="sxs-lookup"><span data-stu-id="14d16-150">**To get help with crontab**</span></span>

`man crontab`

<span data-ttu-id="14d16-151">**現在のユーザーの crontab ファイルの一覧を取得するには**</span><span class="sxs-lookup"><span data-stu-id="14d16-151">**To get a list of crontab file of the current user**</span></span>

`crontab -l`

<span data-ttu-id="14d16-152">**別のユーザーの crontab ファイルの一覧を取得するには**</span><span class="sxs-lookup"><span data-stu-id="14d16-152">**To get a list of crontab file of another user**</span></span>

`crontab -u username -l`

<span data-ttu-id="14d16-153">**crontab エントリをバックアップするには**</span><span class="sxs-lookup"><span data-stu-id="14d16-153">**To backup crontab entries**</span></span>

`crontab -l > /var/tmp/cron_backup.dat`

> [!TIP]
> <span data-ttu-id="14d16-154">編集または削除する前に、この操作を行います。</span><span class="sxs-lookup"><span data-stu-id="14d16-154">Do this before you edit or remove.</span></span> <br>

<span data-ttu-id="14d16-155">**crontab エントリを復元するには**</span><span class="sxs-lookup"><span data-stu-id="14d16-155">**To restore crontab entries**</span></span>

`crontab /var/tmp/cron_backup.dat`

<span data-ttu-id="14d16-156">**crontab を編集し、新しいジョブをルート ユーザーとして追加するには**</span><span class="sxs-lookup"><span data-stu-id="14d16-156">**To edit the crontab and add a new job as a root user**</span></span>

`sudo crontab -e`

<span data-ttu-id="14d16-157">**crontab を編集して新しいジョブを追加するには**</span><span class="sxs-lookup"><span data-stu-id="14d16-157">**To edit the crontab and add a new job**</span></span>

`crontab -e`

<span data-ttu-id="14d16-158">**他のユーザーの crontab エントリを編集するには**</span><span class="sxs-lookup"><span data-stu-id="14d16-158">**To edit other user’s crontab entries**</span></span>

`crontab -u username -e`

<span data-ttu-id="14d16-159">**すべての crontab エントリを削除するには**</span><span class="sxs-lookup"><span data-stu-id="14d16-159">**To remove all crontab entries**</span></span>

`crontab -r`

<span data-ttu-id="14d16-160">**他のユーザーの crontab エントリを削除するには**</span><span class="sxs-lookup"><span data-stu-id="14d16-160">**To remove other user’s crontab entries**</span></span>

`crontab -u username -r`

<span data-ttu-id="14d16-161">**説明**</span><span class="sxs-lookup"><span data-stu-id="14d16-161">**Explanation**</span></span>

<pre>
+—————- minute (values: 0 – 59) (special characters: , – * /)  <br>
| +————- hour (values: 0 – 23) (special characters: , – * /) <br>
| | +———- day of month (values: 1 – 31) (special characters: , – * / L W C)  <br>
| | | +——- month (values: 1 – 12) (special characters: ,- * / )  <br>
| | | | +—- day of week (values: 0 – 6) (Sunday=0 or 7) (special characters: , – * / L W C) <br>
| | | | |*****command to be executed
</pre>

