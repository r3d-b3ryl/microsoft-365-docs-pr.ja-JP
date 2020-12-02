---
title: Microsoft クラウドの移行に関する AD FS 移行手順
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
description: '概要: Microsoft クラウドの移行のための Active Directory フェデレーションサービス (AD FS) の移行手順。'
ms.openlocfilehash: 175734851c2838eb2e224a9afb57a600d4ed9523
ms.sourcegitcommit: 38d828ae8d4350ae774a939c8decf30cb36c3bea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/02/2020
ms.locfileid: "49554817"
---
# <a name="ad-fs-migration-steps-for-the-migration-from-microsoft-cloud-deutschland"></a><span data-ttu-id="d4094-103">Microsoft クラウドの移行に関する AD FS 移行手順</span><span class="sxs-lookup"><span data-stu-id="d4094-103">AD FS migration steps for the migration from Microsoft Cloud Deutschland</span></span>

<span data-ttu-id="d4094-104">Active Directory フェデレーションサービス (AD FS) ファームを Microsoft Cloud Deut上陸陸から移行するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="d4094-104">To migrate your Active Directory Federation Services (AD FS) farm from Microsoft Cloud Deutschland:</span></span>

1. <span data-ttu-id="d4094-105">[次の手順に従っ](#backup)て、FF 信頼情報を含む AD FS 設定をバックアップします。</span><span class="sxs-lookup"><span data-stu-id="d4094-105">Back up your AD FS settings including FF trust info with [these steps](#backup).</span></span> <span data-ttu-id="d4094-106">Microsoft Cloud Deut上陸ランドテナント情報のみが含まれていることを示すために、バックアップ **Microsoft cloud Deutschland_Only** に名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="d4094-106">Name the backup **Microsoft Cloud Deutschland_Only** to indicate it only has the Microsoft Cloud Deutschland tenant info.</span></span>
2. <span data-ttu-id="d4094-107">「Microsoft Cloud Deutschland_Only のバックアップを使用して復元をテストする」では、AD FS ファームは、Microsoft Cloud Deut上陸陸のみを引き続き運用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d4094-107">Test the restore using the Microsoft Cloud Deutschland_Only backup, The AD FS farm should continue to operate as Microsoft Cloud Deutschland only.</span></span>
3. <span data-ttu-id="d4094-108">**AD FS > Office 365 サービス** から新しい証明書利用者信頼を作成します。</span><span class="sxs-lookup"><span data-stu-id="d4094-108">Create a new Relying Party trust from **AD FS >  Office 365 services**.</span></span>
4. <span data-ttu-id="d4094-109">AD FS 管理コンソールの **証明書利用者信頼** で、[ **証明書利用者信頼の追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d4094-109">In **Relying Party Trusts** in the AD FS management console, select **Add Relying Party Trust**.</span></span>
5. <span data-ttu-id="d4094-110">証明書利用者信頼の追加ウィザードの [**ようこそ**] ページで、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d4094-110">Select **Next** on the **Welcome** page of the Add Relying Party Trust wizard.</span></span>
6. <span data-ttu-id="d4094-111">[ **データソースの選択** ] ページで、[ **証明書利用者が公開したオンラインまたはローカルネットワークに関するデータをインポート** する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d4094-111">On the **Select Data Source** page, select **Import data about the relying party published online or on a local network**.</span></span> <span data-ttu-id="d4094-112">**フェデレーションメタデータのアドレス (ホスト名または URL)** 値はに設定され `https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml` ます。</span><span class="sxs-lookup"><span data-stu-id="d4094-112">The **Federation metadata address (host name or URL)** value is set to `https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml`.</span></span> <span data-ttu-id="d4094-113">[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d4094-113">Click **Next**.</span></span>
7. <span data-ttu-id="d4094-114">[ **データソースの選択** ] ページで、表示名を入力します。</span><span class="sxs-lookup"><span data-stu-id="d4094-114">On the **Select Data Source** page, type the display name.</span></span> <span data-ttu-id="d4094-115">Microsoft は、 **世界中の Microsoft Office 365 Id プラットフォーム** をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d4094-115">Microsoft recommends **Microsoft Office 365 Identity Platform WorldWide**.</span></span> <span data-ttu-id="d4094-116">[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d4094-116">Click **Next**.</span></span>
8. <span data-ttu-id="d4094-117">[**多要素認証を構成しますか?**] で [**次へ**] をクリックし、[**発行の承認規則**] を選択して、**信頼ページを追加する準備ができ** ました。</span><span class="sxs-lookup"><span data-stu-id="d4094-117">Click **Next** on the **Configure Multi-factor Authentication Now?**, **Choose Issuance Authorization Rules**, and **Ready to Add Trust** pages.</span></span>
9. <span data-ttu-id="d4094-118">[**完了**] ページで [**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d4094-118">Click **Close** on the **Finish** page.</span></span>

<span data-ttu-id="d4094-119">ウィザードを閉じると、Office 365 services Est への証明書利用者の信頼が確立されます。</span><span class="sxs-lookup"><span data-stu-id="d4094-119">By closing the wizard, the Relying Party Trust to the Office 365 services eSTS is established.</span></span> <span data-ttu-id="d4094-120">ただし、発行変換ルールは確立されません。</span><span class="sxs-lookup"><span data-stu-id="d4094-120">However, no Issuance Transform rules are established.</span></span>

<span data-ttu-id="d4094-121">[AD FS ヘルプ](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator)を使用して、正しい発行変換ルールを生成できます。</span><span class="sxs-lookup"><span data-stu-id="d4094-121">You can use [AD FS Help](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) to generate the correct Issuance Transform rules.</span></span> <span data-ttu-id="d4094-122">AD FS ヘルプを使用して作成されたクレームルールは、AD FS 管理コンソールまたは PowerShell を使用して手動で追加できます。</span><span class="sxs-lookup"><span data-stu-id="d4094-122">The generated claim rules created with AD FS Help can either be manually added through the AD FS management console or with PowerShell.</span></span> <span data-ttu-id="d4094-123">AD FS ヘルプは、実行する必要のある必要な PowerShell スクリプトを生成します。</span><span class="sxs-lookup"><span data-stu-id="d4094-123">AD FS Help will generate the necessary PowerShell scripts that need to be run.</span></span>  

1. <span data-ttu-id="d4094-124">スクリプトの右上隅にある [**コピー** ] オプションを使用して、AD FS ヘルプで [**クレームの生成**] を実行し、PowerShell クレーム変換スクリプトをコピーします。</span><span class="sxs-lookup"><span data-stu-id="d4094-124">Run **Generate Claims** on AD FS help and copy the PowerShell claims transformation script using the **Copy** option on the right upper corner of the script.</span></span>
2. <span data-ttu-id="d4094-125">生成された PowerShell を次のように貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="d4094-125">Paste the generated PowerShell into the following:</span></span>

  ```powershell
  $RuleSet = New-AdfsClaimRuleSet -ClaimRule "<AD FS Help generated PSH>"
  Set-AdfsRelyingPartyTrust -TargetName “Microsoft Office 365 Identity Platform WorldWide” -IssuanceTransformRules $RuleSet.ClaimRulesString;
  ```
3.  <span data-ttu-id="d4094-126">完成したスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="d4094-126">Execute the completed script.</span></span>
4.  <span data-ttu-id="d4094-127">2つの証明書利用者信頼が存在することを確認します。1つはワールドワイドで、もう1つは BF 用です。</span><span class="sxs-lookup"><span data-stu-id="d4094-127">Verify that two Relying Party trusts are present; one for worldwide and one for BF.</span></span>
5.  <span data-ttu-id="d4094-128">[次の手順](#backup)を使用して、信頼関係をバックアップします。</span><span class="sxs-lookup"><span data-stu-id="d4094-128">Backup your trusts using [these steps](#backup).</span></span> <span data-ttu-id="d4094-129">「 **Ffandworldwide**」という名前を付けて保存します。</span><span class="sxs-lookup"><span data-stu-id="d4094-129">Save it with the name **FFAndWorldwide**.</span></span>
6.  <span data-ttu-id="d4094-130">バックエンドの移行を完了し、移行プロセス中に AD FS が依然として機能することを確認します。</span><span class="sxs-lookup"><span data-stu-id="d4094-130">Complete your backend migration and verify that AD FS still works during migration process.</span></span>

## <a name="ad-fs-disaster-recovery-wid-database"></a><span data-ttu-id="d4094-131">AD FS の障害復旧 (WID データベース)</span><span class="sxs-lookup"><span data-stu-id="d4094-131">AD FS Disaster Recovery (WID Database)</span></span>

<span data-ttu-id="d4094-132">障害が発生した ad fs ファームを復元するには、 [ラピッド復元ツール](https://docs.microsoft.com/windows-server/identity/ad-fs/operations/ad-fs-rapid-restore-tool) を活用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d4094-132">To restore the AD FS farm in a disaster [AD FS Rapid Restore Tool](https://docs.microsoft.com/windows-server/identity/ad-fs/operations/ad-fs-rapid-restore-tool) needs to be leveraged.</span></span> <span data-ttu-id="d4094-133">そのため、ツールをダウンロードしてから、移行の開始前に実行する必要があります。バックアップは、作成して安全に保存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d4094-133">Therefore, the tool must be downloaded and before the start of the migration a backup must be created and safely stored.</span></span> <span data-ttu-id="d4094-134">この例 (TAT 環境) では、ファームをバックアップするために次のコマンドが実行されています。</span><span class="sxs-lookup"><span data-stu-id="d4094-134">In this example (TAT environments) the following commands have been run to back up the farm:</span></span>

<h2 id="backup"></h2>

### <a name="back-up-an-ad-fs-farm"></a><span data-ttu-id="d4094-135">AD FS ファームをバックアップする</span><span class="sxs-lookup"><span data-stu-id="d4094-135">Back up an AD FS Farm</span></span>

1. <span data-ttu-id="d4094-136">プライマリ AD FS サーバーに AD FS ラピッド Restore ツールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="d4094-136">Install the AD FS Rapid Restore Tool on the primary AD FS server.</span></span>
2. <span data-ttu-id="d4094-137">このコマンドを使用して、PowerShell セッションでモジュールをインポートします。</span><span class="sxs-lookup"><span data-stu-id="d4094-137">Import the module in a PowerShell session with this command.</span></span>

  ```powershell
  Import-Module "C:\Program Files (x86)\ADFS Rapid Recreation Tool\ADFSRapidRecreationTool.dll"
  ```
3. <span data-ttu-id="d4094-138">バックアップコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="d4094-138">Run the backup command:</span></span>

  ```powershell
  Backup-ADFS -StorageType "FileSystem" -storagePath "<Storage path of backup>" -EncryptionPassword "<password>" -BackupComment "Restore Doku" -BackupDKM
  ```

4. <span data-ttu-id="d4094-139">目的の場所にバックアップを安全に保存します。</span><span class="sxs-lookup"><span data-stu-id="d4094-139">Store the backup safely on a desired destination.</span></span> 

### <a name="restore-an-ad-fs-farm"></a><span data-ttu-id="d4094-140">AD FS ファームを復元する</span><span class="sxs-lookup"><span data-stu-id="d4094-140">Restore an AD FS Farm</span></span>

<span data-ttu-id="d4094-141">ファームが完全に失敗し、古いファームに戻す方法がない場合は、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="d4094-141">If your farm failed completely and there is no way to return to the old farm, do the following.</span></span> 

1. <span data-ttu-id="d4094-142">以前に生成および保存されたバックアップを新しいプライマリ AD FS サーバーに移動します。</span><span class="sxs-lookup"><span data-stu-id="d4094-142">Move the previously generated and stored backup to the new primary AD FS server.</span></span>
2. <span data-ttu-id="d4094-143">次の `Restore-ADFS` PowerShell コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="d4094-143">Run the following `Restore-ADFS` PowerShell command.</span></span> <span data-ttu-id="d4094-144">必要に応じて、AD FS SSL 証明書を事前にインポートします。</span><span class="sxs-lookup"><span data-stu-id="d4094-144">If necessary, import the AD FS SSL certificate beforehand.</span></span>

  ```powershell
  Restore-ADFS -StorageType "FileSystem" -StoragePath "<Path to Backup>" -DecryptionPassword "<password>" -GroupServiceAccountIdentifier "<gMSA>" -DBConnectionString "WID" -RestoreDKM
  ```

3. <span data-ttu-id="d4094-145">新しい DNS レコードまたはロードバランサーを新しい AD FS サーバーの場所にします。</span><span class="sxs-lookup"><span data-stu-id="d4094-145">Point your new DNS records or load balancer to the new AD FS servers.</span></span>

## <a name="more-information"></a><span data-ttu-id="d4094-146">詳細情報</span><span class="sxs-lookup"><span data-stu-id="d4094-146">More information</span></span>

<span data-ttu-id="d4094-147">はじめに:</span><span class="sxs-lookup"><span data-stu-id="d4094-147">Getting started:</span></span>

- [<span data-ttu-id="d4094-148">新しいドイツ語のデータセンターリージョンの Microsoft Cloud Deutランドから Office 365 サービスへの移行</span><span class="sxs-lookup"><span data-stu-id="d4094-148">Migration from Microsoft Cloud Deutschland to Office 365 services in the new German datacenter regions</span></span>](ms-cloud-germany-transition.md)
- [<span data-ttu-id="d4094-149">Microsoft Cloud Deutschland 移行アシスタント</span><span class="sxs-lookup"><span data-stu-id="d4094-149">Microsoft Cloud Deutschland Migration Assistance</span></span>](https://aka.ms/germanymigrateassist)
- [<span data-ttu-id="d4094-150">移行のオプトイン方法</span><span class="sxs-lookup"><span data-stu-id="d4094-150">How to opt-in for migration</span></span>](ms-cloud-germany-migration-opt-in.md)
- [<span data-ttu-id="d4094-151">移行中の顧客の利便性</span><span class="sxs-lookup"><span data-stu-id="d4094-151">Customer experience during the migration</span></span>](ms-cloud-germany-transition-experience.md)

<span data-ttu-id="d4094-152">遷移を移動します。</span><span class="sxs-lookup"><span data-stu-id="d4094-152">Moving through the transition:</span></span>

- [<span data-ttu-id="d4094-153">移行フェーズのアクションと影響</span><span class="sxs-lookup"><span data-stu-id="d4094-153">Migration phases actions and impacts</span></span>](ms-cloud-germany-transition-phases.md)
- [<span data-ttu-id="d4094-154">その他の準備作業</span><span class="sxs-lookup"><span data-stu-id="d4094-154">Additional pre-work</span></span>](ms-cloud-germany-transition-add-pre-work.md)
- <span data-ttu-id="d4094-155">[サービス](ms-cloud-germany-transition-add-general.md)、[デバイス](ms-cloud-germany-transition-add-devices.md)、[エクスペリエンス](ms-cloud-germany-transition-add-experience.md)、 [AD FS](ms-cloud-germany-transition-add-adfs.md)の追加情報。</span><span class="sxs-lookup"><span data-stu-id="d4094-155">Additional information for [services](ms-cloud-germany-transition-add-general.md), [devices](ms-cloud-germany-transition-add-devices.md), [experiences](ms-cloud-germany-transition-add-experience.md), and [AD FS](ms-cloud-germany-transition-add-adfs.md).</span></span>

<span data-ttu-id="d4094-156">クラウドアプリ:</span><span class="sxs-lookup"><span data-stu-id="d4094-156">Cloud apps:</span></span>

- [<span data-ttu-id="d4094-157">Dynamics 365 移行プログラム情報</span><span class="sxs-lookup"><span data-stu-id="d4094-157">Dynamics 365 migration program information</span></span>](https://aka.ms/d365ceoptin)
- [<span data-ttu-id="d4094-158">Power BI 移行プログラム情報</span><span class="sxs-lookup"><span data-stu-id="d4094-158">Power BI migration program information</span></span>](https://aka.ms/pbioptin)
- [<span data-ttu-id="d4094-159">Microsoft Teams へのアップグレードを開始する</span><span class="sxs-lookup"><span data-stu-id="d4094-159">Getting started with your Microsoft Teams upgrade</span></span>](https://aka.ms/SkypeToTeams-Home)
