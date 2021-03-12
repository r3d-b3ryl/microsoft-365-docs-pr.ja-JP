---
title: ADから移行するための FS 移行手順の詳細
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
description: '概要: Microsoft Cloud Deutschland からの移行AD Active Directory フェデレーション サービス (FS) の移行手順について説明します。'
ms.openlocfilehash: 030515227f3abdae82736807a01d1691d2d45552
ms.sourcegitcommit: 3d48e198e706f22ac903b346cadda06b2368dd1e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/11/2021
ms.locfileid: "50727469"
---
# <a name="ad-fs-migration-steps-for-the-migration-from-microsoft-cloud-deutschland"></a><span data-ttu-id="4e62f-103">ADから移行するための FS 移行手順の詳細</span><span class="sxs-lookup"><span data-stu-id="4e62f-103">AD FS migration steps for the migration from Microsoft Cloud Deutschland</span></span>

<span data-ttu-id="4e62f-104">この構成変更は、フェーズ 4 が開始される前にいつでも適用できます。</span><span class="sxs-lookup"><span data-stu-id="4e62f-104">This configuration change can be applied at any time before phase 4 is starting.</span></span>
<span data-ttu-id="4e62f-105">フェーズ 2 が完了すると、構成の変更が機能し、次のような 365 グローバル Officeにサインインできます `https://portal.office.com` 。</span><span class="sxs-lookup"><span data-stu-id="4e62f-105">Once phase 2 is completed the configuration change will work and you are able to sign in to Office 365 Global endpoints such as `https://portal.office.com`.</span></span> <span data-ttu-id="4e62f-106">フェーズ 2 より前に構成変更を実装する場合、Office 365 グローバル エンドポイントはまだ動作しませんが、新しい証明書利用者信頼は Active Directory フェデレーション サービス (AD FS) 構成の一部です。</span><span class="sxs-lookup"><span data-stu-id="4e62f-106">If you are implementing the configuration change before phase 2, the Office 365 Global endpoints will _not yet work_ but the new relying party trust is still part of your Active Directory Federation Services (AD FS) configuration.</span></span>

<span data-ttu-id="4e62f-107">Microsoft Cloud Deutschland AD FS ファームを移行するには、次の方法を実行します。</span><span class="sxs-lookup"><span data-stu-id="4e62f-107">To migrate your AD FS farm from Microsoft Cloud Deutschland:</span></span>

1. <span data-ttu-id="4e62f-108">FF 信頼情報を含AD FS 設定を次の手順で [バックアップします](#backup)。</span><span class="sxs-lookup"><span data-stu-id="4e62f-108">Back up your AD FS settings including FF trust info with [these steps](#backup).</span></span> <span data-ttu-id="4e62f-109">バックアップに **Microsoft Cloud ドメインDeutschland_Only** 名を付け、Microsoft Cloud Deutschland テナント情報のみを持つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="4e62f-109">Name the backup **Microsoft Cloud Deutschland_Only** to indicate it only has the Microsoft Cloud Deutschland tenant info.</span></span>
2. <span data-ttu-id="4e62f-110">Microsoft Cloud Deutschland_Onlyバックアップを使用して復元をテストしますAD FS ファームは引き続き Microsoft Cloud Deutschland としてのみ動作する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4e62f-110">Test the restore using the Microsoft Cloud Deutschland_Only backup, The AD FS farm should continue to operate as Microsoft Cloud Deutschland only.</span></span>

<span data-ttu-id="4e62f-111">FS バックアップを完了してテストしたらAD手順を実行して、ADFS 構成に新しい証明書利用者信頼を追加します。</span><span class="sxs-lookup"><span data-stu-id="4e62f-111">Once you have completed and tested the AD FS backup, perform the following steps to add a new relying party trust to your ADFS configuration:</span></span>

1. <span data-ttu-id="4e62f-112">FS 管理コンソールAD開く</span><span class="sxs-lookup"><span data-stu-id="4e62f-112">Open the AD FS management console</span></span>
2. <span data-ttu-id="4e62f-113">ADFS 管理コンソールの左側のウィンドウで **、[ADFS]**、[信頼関係] の順に展開し、[証明書利用者 **の信頼] を展開します。**</span><span class="sxs-lookup"><span data-stu-id="4e62f-113">In the left pane of the ADFS management console, expand **ADFS**, then **Trust Relationships**, then **Relying Party Trusts**</span></span>
3. <span data-ttu-id="4e62f-114">右側のウィンドウで、[証明書利用者 **信頼の追加]を選択します。**</span><span class="sxs-lookup"><span data-stu-id="4e62f-114">In the right pane, select **Add Relying Party Trust...**</span></span>
4. <span data-ttu-id="4e62f-115">証明書 **利用者信頼** の追加 **ウィザードの [** ようこそ] ページで [次へ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4e62f-115">Select **Next** on the **Welcome** page of the Add Relying Party Trust wizard.</span></span>
5. <span data-ttu-id="4e62f-116">[データ **ソースの選択] ページ** で、[オンラインまたはローカル ネットワークで発行された証明書利用者に関するデータのインポート **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="4e62f-116">On the **Select Data Source** page, select **Import data about the relying party published online or on a local network**.</span></span> <span data-ttu-id="4e62f-117">フェデレーション **メタデータ アドレス (ホスト名または URL)** の値をに設定する必要があります `https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml` 。</span><span class="sxs-lookup"><span data-stu-id="4e62f-117">The **Federation metadata address (host name or URL)** value must be set to `https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml`.</span></span> <span data-ttu-id="4e62f-118">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4e62f-118">Then, click **Next**.</span></span>
6. <span data-ttu-id="4e62f-119">[データ **ソースの選択]** ページで、365 Identity Platform WorldWide などのMicrosoft Office **を入力します**。</span><span class="sxs-lookup"><span data-stu-id="4e62f-119">On the **Select Data Source** page, type the display name such as **Microsoft Office 365 Identity Platform WorldWide**.</span></span> <span data-ttu-id="4e62f-120">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4e62f-120">Then, click **Next**.</span></span>
7. <span data-ttu-id="4e62f-121">[多要素認証を今すぐ構成する **]** ウィザード ページで、認証要件に応じて適切な選択肢を選択します。</span><span class="sxs-lookup"><span data-stu-id="4e62f-121">On the wizard page **Configure Multi-factor Authentication Now?**, select the appropriate choice according to your authentication requirements.</span></span> <span data-ttu-id="4e62f-122">既定に固執する場合は、[この証明書利用者信頼の多要素認証設定をこの時点で構成しない] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="4e62f-122">If you stick with the default, select **I don't want to configure multi-factor authentication settings for this relying party trust at this time**.</span></span> <span data-ttu-id="4e62f-123">必要に応じ、後でこの設定を変更できます。</span><span class="sxs-lookup"><span data-stu-id="4e62f-123">You can change this setting later if you want to.</span></span>
8. <span data-ttu-id="4e62f-124">[発行承認 **ルールの選択]** で、[すべてのユーザーにこの証明書利用者へのアクセスを許可する] をオンにし、[次へ] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="4e62f-124">On the **Choose Issuance Authorization Rules**, keep **Permit all users to access this relying party** selected click **Next**</span></span>
9. <span data-ttu-id="4e62f-125">[ **信頼の準備** 完了] **ページの [次へ] をクリック** して、ウィザードを完了します。</span><span class="sxs-lookup"><span data-stu-id="4e62f-125">Click **Next** on the **Ready to Add Trust** page to complete the wizard.</span></span>
10. <span data-ttu-id="4e62f-126">[完了 **] ページで** [ **閉じる] をクリック** します。</span><span class="sxs-lookup"><span data-stu-id="4e62f-126">Click **Close** on the **Finish** page.</span></span>

<span data-ttu-id="4e62f-127">ウィザードを閉じると、証明書利用者信頼と 365 グローバル Officeサービスが確立されます。</span><span class="sxs-lookup"><span data-stu-id="4e62f-127">By closing the wizard, the Relying Party Trust with the Office 365 Global services is established.</span></span> <span data-ttu-id="4e62f-128">ただし、発行変換ルールはまだ構成されていません。</span><span class="sxs-lookup"><span data-stu-id="4e62f-128">However, no Issuance Transform rules are configured yet.</span></span>

<span data-ttu-id="4e62f-129">FS ヘルプを [ADして、](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) 正しい発行変換ルールを生成できます。</span><span class="sxs-lookup"><span data-stu-id="4e62f-129">You can use [AD FS Help](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) to generate the correct Issuance Transform rules.</span></span> <span data-ttu-id="4e62f-130">AD FS ヘルプで作成された生成されたクレーム ルールは、AD FS 管理コンソールまたは PowerShell を使用して手動で追加できます。</span><span class="sxs-lookup"><span data-stu-id="4e62f-130">The generated claim rules created with AD FS Help can either be manually added through the AD FS management console or with PowerShell.</span></span> <span data-ttu-id="4e62f-131">AD FS ヘルプは、実行する必要がある必要がある PowerShell スクリプトを生成します。</span><span class="sxs-lookup"><span data-stu-id="4e62f-131">AD FS Help will generate the necessary PowerShell scripts that need to be executed.</span></span>  

<!--
    Question from ckinder
    is step #3 true?
    how to verify step 5? Need more information!
-->
1. <span data-ttu-id="4e62f-132">FS **ヘルプで** クレームAD実行し、スクリプトの右上隅にある [コピー] オプションを使用してPowerShell クレーム変換スクリプトをコピーします。</span><span class="sxs-lookup"><span data-stu-id="4e62f-132">Run **Generate Claims** on AD FS help and copy the PowerShell claims transformation script using the **Copy** option on the right upper corner of the script.</span></span>
2. <span data-ttu-id="4e62f-133">優先するテキスト エディターを開き、PowerShell スクリプトを新しいテキスト ウィンドウに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="4e62f-133">Open your preferred text editor and paste the PowerShell script into a new text window.</span></span>
3. <span data-ttu-id="4e62f-134">手順 2 から貼り付けスクリプトの末尾に次の PowerShell 行を追加する</span><span class="sxs-lookup"><span data-stu-id="4e62f-134">Add the following PowerShell lines to the end of the pasted script from step 2</span></span>
    ```powershell
    $authzRules = "=>issue(Type = `"http://schemas.microsoft.com/authorization/claims/permit`", Value = `"true`"); "
    $RuleSet = New-AdfsClaimRuleSet -ClaimRule "<AD FS Help generated PSH>"
    Set-AdfsRelyingPartyTrust -TargetName “Microsoft Office 365 Identity Platform WorldWide” -IssuanceTransformRules $RuleSet.ClaimRulesString -IssuanceAuthorizationRules $authzRules
    ```
4. <span data-ttu-id="4e62f-135">PowerShell スクリプトを安全に実行します。</span><span class="sxs-lookup"><span data-stu-id="4e62f-135">Safe and execute the PowerShell script.</span></span>
5. <span data-ttu-id="4e62f-136">2 つの証明書利用者信頼が存在すること。1 つは Microsoft Cloud Deutschland 用、もう 1 つは Office 365 Global サービス用です。</span><span class="sxs-lookup"><span data-stu-id="4e62f-136">Verify that two Relying Party trusts are present; one for the Microsoft Cloud Deutschland and one for the Office 365 Global service.</span></span>
6. <span data-ttu-id="4e62f-137">これらの手順を使用して信頼 [をバックアップします](#backup)。</span><span class="sxs-lookup"><span data-stu-id="4e62f-137">Backup your trusts using [these steps](#backup).</span></span> <span data-ttu-id="4e62f-138">**FFAndWorldwide という名前で保存します**。</span><span class="sxs-lookup"><span data-stu-id="4e62f-138">Save it with the name **FFAndWorldwide**.</span></span>
7. <span data-ttu-id="4e62f-139">バックエンドの移行を完了し、移行AD FS が引き続き動作します。</span><span class="sxs-lookup"><span data-stu-id="4e62f-139">Complete your backend migration and verify that AD FS still works during the migration process.</span></span>

## <a name="ad-fs-disaster-recovery-wid-database"></a><span data-ttu-id="4e62f-140">AD FS 障害復旧 (WID データベース)</span><span class="sxs-lookup"><span data-stu-id="4e62f-140">AD FS Disaster Recovery (WID Database)</span></span>

<span data-ttu-id="4e62f-141">障害時にAD FS ファームを復元するにはAD [FS Rapid Restore Tool](https://docs.microsoft.com/windows-server/identity/ad-fs/operations/ad-fs-rapid-restore-tool) を活用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4e62f-141">To restore the AD FS farm in a disaster [AD FS Rapid Restore Tool](https://docs.microsoft.com/windows-server/identity/ad-fs/operations/ad-fs-rapid-restore-tool) needs to be leveraged.</span></span> <span data-ttu-id="4e62f-142">したがって、ツールをダウンロードし、移行の開始前にバックアップを作成して安全に保存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4e62f-142">Therefore, the tool must be downloaded and before the start of the migration a backup must be created and safely stored.</span></span> <span data-ttu-id="4e62f-143">この例 (TAT 環境) では、ファームをバックアップするために次のコマンドが実行されています。</span><span class="sxs-lookup"><span data-stu-id="4e62f-143">In this example (TAT environments) the following commands have been run to back up the farm:</span></span>

<h2 id="backup"></h2>

### <a name="back-up-an-ad-fs-farm"></a><span data-ttu-id="4e62f-144">FS ファームADバックアップする</span><span class="sxs-lookup"><span data-stu-id="4e62f-144">Back up an AD FS Farm</span></span>

1. <span data-ttu-id="4e62f-145">FS サーバー AD FS ラピッド 復元ツールをインストールADします。</span><span class="sxs-lookup"><span data-stu-id="4e62f-145">Install the AD FS Rapid Restore Tool on the primary AD FS server.</span></span>
2. <span data-ttu-id="4e62f-146">このコマンドを使用して、PowerShell セッションでモジュールをインポートします。</span><span class="sxs-lookup"><span data-stu-id="4e62f-146">Import the module in a PowerShell session with this command.</span></span>
    ```powershell
    Import-Module "C:\Program Files (x86)\ADFS Rapid Recreation Tool\ADFSRapidRecreationTool.dll"
    ```
3. <span data-ttu-id="4e62f-147">バックアップ コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="4e62f-147">Run the backup command:</span></span>
    ```powershell
    Backup-ADFS -StorageType "FileSystem" -storagePath "<Storage path of backup>" -EncryptionPassword "<password>" -BackupComment "Restore Doku" -BackupDKM
    ```
4. <span data-ttu-id="4e62f-148">バックアップを目的の宛先に安全に保存します。</span><span class="sxs-lookup"><span data-stu-id="4e62f-148">Store the backup safely on a desired destination.</span></span>

### <a name="restore-an-ad-fs-farm"></a><span data-ttu-id="4e62f-149">FS ファームAD復元する</span><span class="sxs-lookup"><span data-stu-id="4e62f-149">Restore an AD FS Farm</span></span>

<span data-ttu-id="4e62f-150">ファームが完全に失敗し、古いファームに戻る方法がない場合は、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="4e62f-150">If your farm failed completely and there is no way to return to the old farm, do the following.</span></span> 

1. <span data-ttu-id="4e62f-151">以前に生成され保存されたバックアップを FS サーバーの新しいプライマリ AD移動します。</span><span class="sxs-lookup"><span data-stu-id="4e62f-151">Move the previously generated and stored backup to the new primary AD FS server.</span></span>
2. <span data-ttu-id="4e62f-152">次の `Restore-ADFS` PowerShell コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="4e62f-152">Run the following `Restore-ADFS` PowerShell command.</span></span> <span data-ttu-id="4e62f-153">必要に応じて、事前AD FS SSL 証明書をインポートします。</span><span class="sxs-lookup"><span data-stu-id="4e62f-153">If necessary, import the AD FS SSL certificate beforehand.</span></span>

    ```powershell
    Restore-ADFS -StorageType "FileSystem" -StoragePath "<Path to Backup>" -DecryptionPassword "<password>" -GroupServiceAccountIdentifier "<gMSA>" -DBConnectionString "WID" -RestoreDKM
    ```

3. <span data-ttu-id="4e62f-154">新しい DNS レコードまたはロード バランサーを FS サーバーの新しいADポイントします。</span><span class="sxs-lookup"><span data-stu-id="4e62f-154">Point your new DNS records or load balancer to the new AD FS servers.</span></span>

## <a name="more-information"></a><span data-ttu-id="4e62f-155">詳細情報</span><span class="sxs-lookup"><span data-stu-id="4e62f-155">More information</span></span>

<span data-ttu-id="4e62f-156">はじめに:</span><span class="sxs-lookup"><span data-stu-id="4e62f-156">Getting started:</span></span>

- [<span data-ttu-id="4e62f-157">新しいドイツのデータセンター地域Office 365 サービスへの Microsoft Cloud Deutschland からの移行</span><span class="sxs-lookup"><span data-stu-id="4e62f-157">Migration from Microsoft Cloud Deutschland to Office 365 services in the new German datacenter regions</span></span>](ms-cloud-germany-transition.md)
- [<span data-ttu-id="4e62f-158">Microsoft Cloud Deutschland 移行アシスタント</span><span class="sxs-lookup"><span data-stu-id="4e62f-158">Microsoft Cloud Deutschland Migration Assistance</span></span>](https://aka.ms/germanymigrateassist)
- [<span data-ttu-id="4e62f-159">移行のオプトイン方法</span><span class="sxs-lookup"><span data-stu-id="4e62f-159">How to opt-in for migration</span></span>](ms-cloud-germany-migration-opt-in.md)
- [<span data-ttu-id="4e62f-160">移行中のカスタマー エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="4e62f-160">Customer experience during the migration</span></span>](ms-cloud-germany-transition-experience.md)

<span data-ttu-id="4e62f-161">切り替えの移動:</span><span class="sxs-lookup"><span data-stu-id="4e62f-161">Moving through the transition:</span></span>

- [<span data-ttu-id="4e62f-162">移行フェーズのアクションと影響</span><span class="sxs-lookup"><span data-stu-id="4e62f-162">Migration phases actions and impacts</span></span>](ms-cloud-germany-transition-phases.md)
- [<span data-ttu-id="4e62f-163">その他の作業前</span><span class="sxs-lookup"><span data-stu-id="4e62f-163">Additional pre-work</span></span>](ms-cloud-germany-transition-add-pre-work.md)
- <span data-ttu-id="4e62f-164">Azure [AD、デバイス](ms-cloud-germany-transition-add-devices.md)[、](ms-cloud-germany-transition-azure-ad.md)[エクスペリエンス](ms-cloud-germany-transition-add-experience.md)、および FS のAD[情報](ms-cloud-germany-transition-add-adfs.md)です。</span><span class="sxs-lookup"><span data-stu-id="4e62f-164">Additional information for [Azure AD](ms-cloud-germany-transition-azure-ad.md), [devices](ms-cloud-germany-transition-add-devices.md), [experiences](ms-cloud-germany-transition-add-experience.md), and [AD FS](ms-cloud-germany-transition-add-adfs.md).</span></span>

<span data-ttu-id="4e62f-165">クラウド アプリ:</span><span class="sxs-lookup"><span data-stu-id="4e62f-165">Cloud apps:</span></span>

- [<span data-ttu-id="4e62f-166">Dynamics 365 移行プログラム情報</span><span class="sxs-lookup"><span data-stu-id="4e62f-166">Dynamics 365 migration program information</span></span>](https://aka.ms/d365ceoptin)
- [<span data-ttu-id="4e62f-167">Power BI 移行プログラム情報</span><span class="sxs-lookup"><span data-stu-id="4e62f-167">Power BI migration program information</span></span>](https://aka.ms/pbioptin)
- [<span data-ttu-id="4e62f-168">Microsoft Teams へのアップグレードを開始する</span><span class="sxs-lookup"><span data-stu-id="4e62f-168">Getting started with your Microsoft Teams upgrade</span></span>](https://aka.ms/SkypeToTeams-Home)
