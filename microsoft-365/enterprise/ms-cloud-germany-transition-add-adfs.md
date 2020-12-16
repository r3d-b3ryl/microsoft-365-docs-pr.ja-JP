---
title: AD Microsoft Cloud Deutschland からの移行に関する FS 移行手順を確認する
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/01/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: '概要: Microsoft Cloud Deutschland から移行するための Active Directory フェデレーション サービス (AD FS) 移行手順。'
ms.openlocfilehash: c946ec3c0772cf95ab696266475b50959d682ef2
ms.sourcegitcommit: 849b365bd3eaa9f3c3a9ef9f5973ef81af9156fa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/16/2020
ms.locfileid: "49688667"
---
# <a name="ad-fs-migration-steps-for-the-migration-from-microsoft-cloud-deutschland"></a><span data-ttu-id="163c8-103">AD Microsoft Cloud Deutschland からの移行に関する FS 移行手順を確認する</span><span class="sxs-lookup"><span data-stu-id="163c8-103">AD FS migration steps for the migration from Microsoft Cloud Deutschland</span></span>

<span data-ttu-id="163c8-104">Active Directory フェデレーション サービス (AD FS) ファームを Microsoft Cloud Deutschland から移行するには、</span><span class="sxs-lookup"><span data-stu-id="163c8-104">To migrate your Active Directory Federation Services (AD FS) farm from Microsoft Cloud Deutschland:</span></span>

1. <span data-ttu-id="163c8-105">以下の手順をAD FF 信頼情報を含む FS 設定を [バックアップします](#backup)。</span><span class="sxs-lookup"><span data-stu-id="163c8-105">Back up your AD FS settings including FF trust info with [these steps](#backup).</span></span> <span data-ttu-id="163c8-106">バックアップに **Microsoft Cloud Deutschland_Only** 名を付け、Microsoft Cloud Deutschland テナント情報のみを含む必要があります。</span><span class="sxs-lookup"><span data-stu-id="163c8-106">Name the backup **Microsoft Cloud Deutschland_Only** to indicate it only has the Microsoft Cloud Deutschland tenant info.</span></span>
2. <span data-ttu-id="163c8-107">Microsoft Cloud Deutschland_Only バックアップを使用して復元をテストします。AD FS ファームは Microsoft Cloud Deutschland としてのみ動作する必要があります。</span><span class="sxs-lookup"><span data-stu-id="163c8-107">Test the restore using the Microsoft Cloud Deutschland_Only backup, The AD FS farm should continue to operate as Microsoft Cloud Deutschland only.</span></span>
3. <span data-ttu-id="163c8-108">FS および 365 サービスから新AD **証明書利用者> Office作成します**。</span><span class="sxs-lookup"><span data-stu-id="163c8-108">Create a new Relying Party trust from **AD FS >  Office 365 services**.</span></span>
4. <span data-ttu-id="163c8-109">FS **管理コンソールの [** 証明書利用者信頼] AD、[証明書利用者信頼の追加 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="163c8-109">In **Relying Party Trusts** in the AD FS management console, select **Add Relying Party Trust**.</span></span>
5. <span data-ttu-id="163c8-110">証明書 **利用者信頼** の **追加ウィザードのウェルカム** ページで [次へ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="163c8-110">Select **Next** on the **Welcome** page of the Add Relying Party Trust wizard.</span></span>
6. <span data-ttu-id="163c8-111">[データ ソース **の選択]** ページで、[オンラインまたはローカル ネットワークで発行された証明書利用者に関するデータ **のインポート] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="163c8-111">On the **Select Data Source** page, select **Import data about the relying party published online or on a local network**.</span></span> <span data-ttu-id="163c8-112">フェデレーション **メタデータ アドレス (ホスト名または URL)** の値が設定されます `https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml` 。</span><span class="sxs-lookup"><span data-stu-id="163c8-112">The **Federation metadata address (host name or URL)** value is set to `https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml`.</span></span> <span data-ttu-id="163c8-113">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="163c8-113">Click **Next**.</span></span>
7. <span data-ttu-id="163c8-114">[データ **ソースの選択] ページ** で、表示名を入力します。</span><span class="sxs-lookup"><span data-stu-id="163c8-114">On the **Select Data Source** page, type the display name.</span></span> <span data-ttu-id="163c8-115">Microsoft では **、Microsoft Office 365 Identity Platform WorldWide を使用する方法をお勧めします**。</span><span class="sxs-lookup"><span data-stu-id="163c8-115">Microsoft recommends **Microsoft Office 365 Identity Platform WorldWide**.</span></span> <span data-ttu-id="163c8-116">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="163c8-116">Click **Next**.</span></span>
8. <span data-ttu-id="163c8-117">[**今すぐ多** 要素認証を構成しますか **?]** 、[発行承認規則]、および [信頼の追加の準備完了] ページの [次へ **] をクリック** します。</span><span class="sxs-lookup"><span data-stu-id="163c8-117">Click **Next** on the **Configure Multi-factor Authentication Now?**, **Choose Issuance Authorization Rules**, and **Ready to Add Trust** pages.</span></span>
9. <span data-ttu-id="163c8-118">[完了 **] ページ** で [閉じる] **をクリック** します。</span><span class="sxs-lookup"><span data-stu-id="163c8-118">Click **Close** on the **Finish** page.</span></span>

<span data-ttu-id="163c8-119">ウィザードを閉じると、証明書利用者信頼が Office 365 サービス eSTS に確立されます。</span><span class="sxs-lookup"><span data-stu-id="163c8-119">By closing the wizard, the Relying Party Trust to the Office 365 services eSTS is established.</span></span> <span data-ttu-id="163c8-120">ただし、発行変換ルールは確立されません。</span><span class="sxs-lookup"><span data-stu-id="163c8-120">However, no Issuance Transform rules are established.</span></span>

<span data-ttu-id="163c8-121">適切な発行変換 [AD FS](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) ヘルプを使用して生成できます。</span><span class="sxs-lookup"><span data-stu-id="163c8-121">You can use [AD FS Help](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) to generate the correct Issuance Transform rules.</span></span> <span data-ttu-id="163c8-122">AD FS ヘルプで作成された生成された要求ルールは、AD FS 管理コンソールまたは PowerShell を使用して手動で追加できます。</span><span class="sxs-lookup"><span data-stu-id="163c8-122">The generated claim rules created with AD FS Help can either be manually added through the AD FS management console or with PowerShell.</span></span> <span data-ttu-id="163c8-123">AD FS ヘルプでは、実行する必要がある必要がある PowerShell スクリプトが生成されます。</span><span class="sxs-lookup"><span data-stu-id="163c8-123">AD FS Help will generate the necessary PowerShell scripts that need to be run.</span></span>  

1. <span data-ttu-id="163c8-124">AD  FS ヘルプで要求の生成を実行し、スクリプトの右上隅にある [コピー]オプションを使用して PowerShell クレーム変換スクリプトをコピーします。</span><span class="sxs-lookup"><span data-stu-id="163c8-124">Run **Generate Claims** on AD FS help and copy the PowerShell claims transformation script using the **Copy** option on the right upper corner of the script.</span></span>
2. <span data-ttu-id="163c8-125">生成された PowerShell を次の場所に貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="163c8-125">Paste the generated PowerShell into the following:</span></span>

  ```powershell
  $RuleSet = New-AdfsClaimRuleSet -ClaimRule "<AD FS Help generated PSH>"
  Set-AdfsRelyingPartyTrust -TargetName “Microsoft Office 365 Identity Platform WorldWide” -IssuanceTransformRules $RuleSet.ClaimRulesString;
  ```
3.  <span data-ttu-id="163c8-126">完成したスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="163c8-126">Execute the completed script.</span></span>
4.  <span data-ttu-id="163c8-127">2 つの証明書利用者信頼が存在すること確認します。1 つは世界中向け、もう 1 つは BF 用です。</span><span class="sxs-lookup"><span data-stu-id="163c8-127">Verify that two Relying Party trusts are present; one for worldwide and one for BF.</span></span>
5.  <span data-ttu-id="163c8-128">以下の手順を使用して信頼 [をバックアップします](#backup)。</span><span class="sxs-lookup"><span data-stu-id="163c8-128">Backup your trusts using [these steps](#backup).</span></span> <span data-ttu-id="163c8-129">**FFAndWorldwide という名前で保存します**。</span><span class="sxs-lookup"><span data-stu-id="163c8-129">Save it with the name **FFAndWorldwide**.</span></span>
6.  <span data-ttu-id="163c8-130">バックエンドの移行を完了し、移行プロセスAD FS が引き続き動作する必要があります。</span><span class="sxs-lookup"><span data-stu-id="163c8-130">Complete your backend migration and verify that AD FS still works during migration process.</span></span>

## <a name="ad-fs-disaster-recovery-wid-database"></a><span data-ttu-id="163c8-131">AD FS 障害復旧 (WID データベース)</span><span class="sxs-lookup"><span data-stu-id="163c8-131">AD FS Disaster Recovery (WID Database)</span></span>

<span data-ttu-id="163c8-132">障害時に AD FS ファームを復元 [AD FS 迅速復元ツール](https://docs.microsoft.com/windows-server/identity/ad-fs/operations/ad-fs-rapid-restore-tool) を利用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="163c8-132">To restore the AD FS farm in a disaster [AD FS Rapid Restore Tool](https://docs.microsoft.com/windows-server/identity/ad-fs/operations/ad-fs-rapid-restore-tool) needs to be leveraged.</span></span> <span data-ttu-id="163c8-133">したがって、ツールをダウンロードし、移行の開始前にバックアップを作成して安全に保存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="163c8-133">Therefore, the tool must be downloaded and before the start of the migration a backup must be created and safely stored.</span></span> <span data-ttu-id="163c8-134">この例 (TAT 環境) では、次のコマンドを実行してファームをバックアップしています。</span><span class="sxs-lookup"><span data-stu-id="163c8-134">In this example (TAT environments) the following commands have been run to back up the farm:</span></span>

<h2 id="backup"></h2>

### <a name="back-up-an-ad-fs-farm"></a><span data-ttu-id="163c8-135">AD FS ファームをバックアップする</span><span class="sxs-lookup"><span data-stu-id="163c8-135">Back up an AD FS Farm</span></span>

1. <span data-ttu-id="163c8-136">プライマリ AD FS サーバーに AD FS Rapid Restore Tool をインストールします。</span><span class="sxs-lookup"><span data-stu-id="163c8-136">Install the AD FS Rapid Restore Tool on the primary AD FS server.</span></span>
2. <span data-ttu-id="163c8-137">次のコマンドを使用して、PowerShell セッションでモジュールをインポートします。</span><span class="sxs-lookup"><span data-stu-id="163c8-137">Import the module in a PowerShell session with this command.</span></span>

  ```powershell
  Import-Module "C:\Program Files (x86)\ADFS Rapid Recreation Tool\ADFSRapidRecreationTool.dll"
  ```
3. <span data-ttu-id="163c8-138">バックアップ コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="163c8-138">Run the backup command:</span></span>

  ```powershell
  Backup-ADFS -StorageType "FileSystem" -storagePath "<Storage path of backup>" -EncryptionPassword "<password>" -BackupComment "Restore Doku" -BackupDKM
  ```

4. <span data-ttu-id="163c8-139">目的のバックアップ先にバックアップを安全に保存します。</span><span class="sxs-lookup"><span data-stu-id="163c8-139">Store the backup safely on a desired destination.</span></span> 

### <a name="restore-an-ad-fs-farm"></a><span data-ttu-id="163c8-140">AD FS ファームを復元する</span><span class="sxs-lookup"><span data-stu-id="163c8-140">Restore an AD FS Farm</span></span>

<span data-ttu-id="163c8-141">ファームが完全に失敗し、古いファームに戻る方法がない場合は、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="163c8-141">If your farm failed completely and there is no way to return to the old farm, do the following.</span></span> 

1. <span data-ttu-id="163c8-142">以前に生成および保存したバックアップを、FS サーバーの新しいプライマリ ADに移動します。</span><span class="sxs-lookup"><span data-stu-id="163c8-142">Move the previously generated and stored backup to the new primary AD FS server.</span></span>
2. <span data-ttu-id="163c8-143">次の `Restore-ADFS` PowerShell コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="163c8-143">Run the following `Restore-ADFS` PowerShell command.</span></span> <span data-ttu-id="163c8-144">必要に応じて、事前に AD FS SSL 証明書をインポートします。</span><span class="sxs-lookup"><span data-stu-id="163c8-144">If necessary, import the AD FS SSL certificate beforehand.</span></span>

  ```powershell
  Restore-ADFS -StorageType "FileSystem" -StoragePath "<Path to Backup>" -DecryptionPassword "<password>" -GroupServiceAccountIdentifier "<gMSA>" -DBConnectionString "WID" -RestoreDKM
  ```

3. <span data-ttu-id="163c8-145">新しい DNS レコードまたはロード バランサーが、新しい FS サーバー ADポイントします。</span><span class="sxs-lookup"><span data-stu-id="163c8-145">Point your new DNS records or load balancer to the new AD FS servers.</span></span>

## <a name="more-information"></a><span data-ttu-id="163c8-146">詳細</span><span class="sxs-lookup"><span data-stu-id="163c8-146">More information</span></span>

<span data-ttu-id="163c8-147">はじめに:</span><span class="sxs-lookup"><span data-stu-id="163c8-147">Getting started:</span></span>

- [<span data-ttu-id="163c8-148">Microsoft Cloud Deutschland から新しいドイツのデータセンター リージョンOffice 365 サービスへの移行</span><span class="sxs-lookup"><span data-stu-id="163c8-148">Migration from Microsoft Cloud Deutschland to Office 365 services in the new German datacenter regions</span></span>](ms-cloud-germany-transition.md)
- [<span data-ttu-id="163c8-149">Microsoft Cloud Deutschland 移行アシスタント</span><span class="sxs-lookup"><span data-stu-id="163c8-149">Microsoft Cloud Deutschland Migration Assistance</span></span>](https://aka.ms/germanymigrateassist)
- [<span data-ttu-id="163c8-150">移行のオプトイン方法</span><span class="sxs-lookup"><span data-stu-id="163c8-150">How to opt-in for migration</span></span>](ms-cloud-germany-migration-opt-in.md)
- [<span data-ttu-id="163c8-151">移行中のカスタマー エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="163c8-151">Customer experience during the migration</span></span>](ms-cloud-germany-transition-experience.md)

<span data-ttu-id="163c8-152">移行を進む:</span><span class="sxs-lookup"><span data-stu-id="163c8-152">Moving through the transition:</span></span>

- [<span data-ttu-id="163c8-153">移行フェーズのアクションと影響</span><span class="sxs-lookup"><span data-stu-id="163c8-153">Migration phases actions and impacts</span></span>](ms-cloud-germany-transition-phases.md)
- [<span data-ttu-id="163c8-154">追加の作業前作業</span><span class="sxs-lookup"><span data-stu-id="163c8-154">Additional pre-work</span></span>](ms-cloud-germany-transition-add-pre-work.md)
- <span data-ttu-id="163c8-155">Azure [AD、](ms-cloud-germany-transition-add-devices.md)[デバイス](ms-cloud-germany-transition-azure-ad.md)、[エクスペリエンス、および](ms-cloud-germany-transition-add-experience.md)AD FS[に関する追加情報](ms-cloud-germany-transition-add-adfs.md)。</span><span class="sxs-lookup"><span data-stu-id="163c8-155">Additional information for [Azure AD](ms-cloud-germany-transition-azure-ad.md), [devices](ms-cloud-germany-transition-add-devices.md), [experiences](ms-cloud-germany-transition-add-experience.md), and [AD FS](ms-cloud-germany-transition-add-adfs.md).</span></span>

<span data-ttu-id="163c8-156">クラウド アプリ:</span><span class="sxs-lookup"><span data-stu-id="163c8-156">Cloud apps:</span></span>

- [<span data-ttu-id="163c8-157">Dynamics 365 移行プログラム情報</span><span class="sxs-lookup"><span data-stu-id="163c8-157">Dynamics 365 migration program information</span></span>](https://aka.ms/d365ceoptin)
- [<span data-ttu-id="163c8-158">Power BI 移行プログラム情報</span><span class="sxs-lookup"><span data-stu-id="163c8-158">Power BI migration program information</span></span>](https://aka.ms/pbioptin)
- [<span data-ttu-id="163c8-159">Microsoft Teams へのアップグレードを開始する</span><span class="sxs-lookup"><span data-stu-id="163c8-159">Getting started with your Microsoft Teams upgrade</span></span>](https://aka.ms/SkypeToTeams-Home)
