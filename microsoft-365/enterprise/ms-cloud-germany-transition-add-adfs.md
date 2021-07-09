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
ms.openlocfilehash: c8e784c8e582185b4bdebc0cb359cc4c19503d1a
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339612"
---
# <a name="ad-fs-migration-steps-for-the-migration-from-microsoft-cloud-deutschland"></a><span data-ttu-id="114ec-103">ADから移行するための FS 移行手順の詳細</span><span class="sxs-lookup"><span data-stu-id="114ec-103">AD FS migration steps for the migration from Microsoft Cloud Deutschland</span></span>

<span data-ttu-id="114ec-104">この構成変更は、フェーズ 2 が開始される前にいつでも適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="114ec-104">This configuration change needs to be applied any time before phase 2 is starting.</span></span>
<span data-ttu-id="114ec-105">フェーズ 2 が完了すると、構成の変更が機能し、次のようなグローバル Office 365経由でサインインできます `https://admin.microsoft.com` 。</span><span class="sxs-lookup"><span data-stu-id="114ec-105">Once phase 2 is completed the configuration change will work and you are able to sign in via Office 365 Global endpoints such as `https://admin.microsoft.com`.</span></span> <span data-ttu-id="114ec-106">フェーズ 2 より前に構成変更を実装する場合、Office 365 Global エンドポイントはまだ動作しませんが、新しい証明書利用者信頼は Active Directory フェデレーション サービス (AD FS) 構成の一部です。</span><span class="sxs-lookup"><span data-stu-id="114ec-106">If you are implementing the configuration change before phase 2, the Office 365 Global endpoints will _not yet work_ but the new relying party trust is still part of your Active Directory Federation Services (AD FS) configuration.</span></span>

<span data-ttu-id="114ec-107">Active Directory フェデレーション サービス (AD FS) でフェデレーション認証を使用しているお客様は、移行中にオンプレミスの Active Directory ドメイン サービス (AD DS) を使用するすべての認証に使用される発行者 URI を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="114ec-107">Customers who use federated authentication with Active Directory Federation Services (AD FS) shouldn't make changes to issuer URIs that are used for all authentications with on-premises Active Directory Domain Services (AD DS) during migration.</span></span> <span data-ttu-id="114ec-108">発行者 URI を変更すると、ドメイン内のユーザーの認証エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="114ec-108">Changing issuer URIs will lead to authentication failures for users in the domain.</span></span> <span data-ttu-id="114ec-109">発行者 URI は、FS またはドメインAD管理からフェデレーションに変換される場合、またはその逆に直接変更できます。</span><span class="sxs-lookup"><span data-stu-id="114ec-109">Issuer URIs can be changed directly in AD FS or when a domain is converted from _managed_ to _federated_ and vice-versa.</span></span> <span data-ttu-id="114ec-110">移行された Azure のフェデレーション ドメインを追加、削除、または変換ADすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="114ec-110">We recommend that you do not add, remove, or convert a federated domain in the Azure AD tenant that has been migrated.</span></span> <span data-ttu-id="114ec-111">発行者 URI は、移行が完全に完了した後で変更できます。</span><span class="sxs-lookup"><span data-stu-id="114ec-111">Issuer URIs can be changed after the migration is fully complete.</span></span>

<span data-ttu-id="114ec-112">Microsoft Cloud Deutschland からの移行AD FS ファームを準備するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="114ec-112">To prepare your AD FS farm for the migration from Microsoft Cloud Deutschland perform the following steps:</span></span>

1. <span data-ttu-id="114ec-113">次の手順AD、既存の Microsoft Cloud Deutschland 証明書利用者信頼を含む FS 設定を [バックアップします](#backup)。</span><span class="sxs-lookup"><span data-stu-id="114ec-113">Back up your AD FS settings, including the existing Microsoft Cloud Deutschland Relying Party trust, with [these steps](#backup).</span></span> <span data-ttu-id="114ec-114">バックアップに **MicrosoftCloudDeutschlandOnly** という名前を付け、Microsoft Cloud Deutschland テナント情報のみを持つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="114ec-114">Name the backup **MicrosoftCloudDeutschlandOnly** to indicate it only has the Microsoft Cloud Deutschland tenant info.</span></span>

   > [!NOTE]
   > <span data-ttu-id="114ec-115">バックアップには、Microsoft Cloud Deutschland の既存の証明書利用者信頼Office 365が含まれるだけでなく、それぞれの FS ファームに存在する他のすべての証明書利用者信頼ADされます。</span><span class="sxs-lookup"><span data-stu-id="114ec-115">The backup will not only contain the existing Office 365 Relying Party Trust for Microsoft Cloud Deutschland, but also all other Relying Party Trusts present on the respective AD FS farm.</span></span>

2. <span data-ttu-id="114ec-116">MicrosoftCloudDeutschlandOnly バックアップを使用して復元をテストします。FS ファームAD Microsoft Cloud Deutschland のみとして動作し続ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="114ec-116">Test the restore using the MicrosoftCloudDeutschlandOnly backup, The AD FS farm should continue to operate as Microsoft Cloud Deutschland only.</span></span>

<span data-ttu-id="114ec-117">FS バックアップを完了してテストしたらAD手順を実行して、ADFS 構成に新しい証明書利用者信頼を追加します。</span><span class="sxs-lookup"><span data-stu-id="114ec-117">Once you have completed and tested the AD FS backup, perform the following steps to add a new relying party trust to your ADFS configuration:</span></span>

1. <span data-ttu-id="114ec-118">[AD FS] 管理コンソールを開きます。</span><span class="sxs-lookup"><span data-stu-id="114ec-118">Open the AD FS management console.</span></span>

2. <span data-ttu-id="114ec-119">ADFS 管理コンソールの左側のウィンドウで、[証明書利用者の信頼] **メニューに移動** します。</span><span class="sxs-lookup"><span data-stu-id="114ec-119">In the left pane of the ADFS management console navigate to the **Relying Party Trusts** menu.</span></span>

3. <span data-ttu-id="114ec-120">右側のウィンドウで、[証明書利用者 **信頼の追加]を選択します。**</span><span class="sxs-lookup"><span data-stu-id="114ec-120">In the right pane, select **Add Relying Party Trust...**</span></span>

4. <span data-ttu-id="114ec-121">証明書 **利用者信頼** の追加 **ウィザードの [** ようこそ] ページで [スタート] を選択します。</span><span class="sxs-lookup"><span data-stu-id="114ec-121">Select **Start** on the **Welcome** page of the Add Relying Party Trust wizard.</span></span>

5. <span data-ttu-id="114ec-122">[データ **ソースの選択] ページ** で、[オンラインまたはローカル ネットワークで発行された証明書利用者に関するデータのインポート **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="114ec-122">On the **Select Data Source** page, select **Import data about the relying party published online or on a local network**.</span></span> <span data-ttu-id="114ec-123">フェデレーション **メタデータ アドレス (ホスト名または URL)** の値をに設定する必要があります `https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml` 。</span><span class="sxs-lookup"><span data-stu-id="114ec-123">The **Federation metadata address (host name or URL)** value must be set to `https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml`.</span></span> <span data-ttu-id="114ec-124">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="114ec-124">Click **Next**.</span></span>

6. <span data-ttu-id="114ec-125">[表示 **名の指定] ページ** で、Id プラットフォーム **WorldWide などの表示Microsoft Office 365入力します**。</span><span class="sxs-lookup"><span data-stu-id="114ec-125">On the **Specify Display Name** page, type the display name such as **Microsoft Office 365 Identity Platform WorldWide**.</span></span> <span data-ttu-id="114ec-126">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="114ec-126">Click **Next**.</span></span>

7. <span data-ttu-id="114ec-127">ADFS を使用している場合Windows Server 2012ウィザード ページの [多要素認証を今すぐ構成する **] で**、認証要件に応じて適切な選択肢を選択します。</span><span class="sxs-lookup"><span data-stu-id="114ec-127">If you are using ADFS in Windows Server 2012, on the wizard page **Configure Multi-factor Authentication Now?**, select the appropriate choice according to your authentication requirements.</span></span> <span data-ttu-id="114ec-128">既定に固執する場合は、[この証明書利用者信頼の多要素認証設定をこの時点で構成しない] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="114ec-128">If you stick with the default, select **I don't want to configure multi-factor authentication settings for this relying party trust at this time**.</span></span> <span data-ttu-id="114ec-129">必要に応じ、後でこの設定を変更できます。</span><span class="sxs-lookup"><span data-stu-id="114ec-129">You can change this setting later if you want to.</span></span>

8. <span data-ttu-id="114ec-130">[AD FS 2012: 発行承認ルールの選択]で、[すべてのユーザーにこの証明書利用者へのアクセスを許可する] を選択し、[次へ] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="114ec-130">For AD FS 2012: On the **Choose Issuance Authorization Rules**, keep **Permit all users to access this relying party** selected and click **Next**.</span></span>

9. <span data-ttu-id="114ec-131">[AD FS 2016 および AD FS 2019:  [アクセス制御ポリシーの選択] ページで、適切なアクセス制御ポリシーを選択し、[次へ] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="114ec-131">For AD FS 2016 and AD FS 2019: On the **Choose Access Control Policy** page, select the appropriate access control policy and click **Next**.</span></span> <span data-ttu-id="114ec-132">選択されていない場合、証明書利用者信頼は **機能** しません。</span><span class="sxs-lookup"><span data-stu-id="114ec-132">If none is chosen, the Relying Party Trust will **NOT** work.</span></span>

10. <span data-ttu-id="114ec-133">[ **信頼の準備** 完了] **ページの [次へ] をクリック** して、ウィザードを完了します。</span><span class="sxs-lookup"><span data-stu-id="114ec-133">Click **Next** on the **Ready to Add Trust** page to complete the wizard.</span></span>

11. <span data-ttu-id="114ec-134">[完了 **] ページで** [ **閉じる] をクリック** します。</span><span class="sxs-lookup"><span data-stu-id="114ec-134">Click **Close** on the **Finish** page.</span></span>

<span data-ttu-id="114ec-135">ウィザードを閉じると、証明書利用者信頼とグローバル サービスOffice 365証明書利用者信頼が確立されます。</span><span class="sxs-lookup"><span data-stu-id="114ec-135">By closing the wizard, the Relying Party Trust with the Office 365 Global service is established.</span></span> <span data-ttu-id="114ec-136">ただし、発行変換ルールはまだ構成されていません。</span><span class="sxs-lookup"><span data-stu-id="114ec-136">However, no Issuance Transform rules are configured yet.</span></span>

<span data-ttu-id="114ec-137">FS ヘルプを [ADして、](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) 正しい発行変換ルールを生成できます。</span><span class="sxs-lookup"><span data-stu-id="114ec-137">You can use [AD FS Help](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) to generate the correct Issuance Transform rules.</span></span> <span data-ttu-id="114ec-138">AD FS ヘルプで作成された生成されたクレーム ルールは、AD FS 管理コンソールまたは PowerShell を使用して手動で追加できます。</span><span class="sxs-lookup"><span data-stu-id="114ec-138">The generated claim rules created with AD FS Help can either be manually added through the AD FS management console or with PowerShell.</span></span> <span data-ttu-id="114ec-139">AD FS ヘルプは、実行する必要がある必要がある PowerShell スクリプトを生成します。</span><span class="sxs-lookup"><span data-stu-id="114ec-139">AD FS Help will generate the necessary PowerShell scripts that need to be executed.</span></span>  

> [!NOTE]
> <span data-ttu-id="114ec-140">[AD FS ヘルプは](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) 、製品に含む標準の発行変換ルールを生成します。</span><span class="sxs-lookup"><span data-stu-id="114ec-140">[AD FS Help](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) will generate the standard issuance transform rules that ship with the product.</span></span> <span data-ttu-id="114ec-141">ただし、カスタム発行変換ルールが Microsoft Cloud Deutschland 証明書利用者信頼 (カスタム発行者 URI、非標準不変の ID、その他のカスタマイズなど) に適用されている場合、AD FS ヘルプによって生成されるルールは、Microsoft Cloud Deutschland 証明書利用者信頼に対して現在適用されているカスタム ロジックに適合する方法で変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="114ec-141">However, if custom issuance transform rules are in place in the Microsoft Cloud Deutschland Relying Party Trust (for example, custom issuer URIs, non-standard immutable IDs, or any other customizations), the rules generated by AD FS help must be modified in a way that they fit the custom logic currently in place for the Microsoft Cloud Deutschland relying party trust.</span></span> <span data-ttu-id="114ec-142">これらのカスタマイズが AD FS ヘルプを介して生成されたルールに統合されていない場合 [、Microsoft Office 365](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) **Identity Platform WorldWide** への認証は、フェデレーション ID では機能しない可能性が高い。</span><span class="sxs-lookup"><span data-stu-id="114ec-142">If these customizations are not integrated in the rules generated via [AD FS Help](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator), authentication to **Microsoft Office 365 Identity Platform WorldWide** will most likely **not** work for your federated identities.</span></span>

1. <span data-ttu-id="114ec-143">FS **ヘルプで** クレーム [AD実行](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator)し、スクリプトの右上隅にある [コピー]オプションを使用して PowerShell スクリプトをコピーします。</span><span class="sxs-lookup"><span data-stu-id="114ec-143">Run **Generate Claims** on [AD FS Help](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) and copy the PowerShell script using the **Copy** option on the right upper corner of the script.</span></span>

2. <span data-ttu-id="114ec-144">AD FS ファームで Power AD Shell スクリプトを実行してグローバル証明書利用者信頼を生成する方法については、「AD [FS](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) ヘルプ」で説明されている手順に従います。</span><span class="sxs-lookup"><span data-stu-id="114ec-144">Follow the steps outlined at [AD FS Help](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) on how to run the PowerShell script in your AD FS farm to generate the global Relying Party Trust.</span></span> <span data-ttu-id="114ec-145">スクリプトを実行する前に、生成されたスクリプトの次のコード行を次のように置き換えます。</span><span class="sxs-lookup"><span data-stu-id="114ec-145">Before you run the script, replace the following code lines in the generated script as outlined below:</span></span>

   ```powershell
   # AD FS Help generated value
   $claims = Get-AdfsRelyingPartyTrust -Identifier $(Get-RpIdentifier) | Select-Object IssuanceTransformRules;
   # replace with
   $claims = Get-AdfsRelyingPartyTrust -Identifier urn:federation:MicrosoftOnline | Select-Object IssuanceTransformRules;

   # AD FS Help generated value
   Set-AdfsRelyingPartyTrust -TargetIdentifier $(Get-RpIdentifier) -IssuanceTransformRules $RuleSet.ClaimRulesString;
   # replace with
   Set-AdfsRelyingPartyTrust -TargetIdentifier urn:federation:MicrosoftOnline -IssuanceTransformRules $RuleSet.ClaimRulesString;
   ```

3. <span data-ttu-id="114ec-146">2 つの証明書利用者Ttrustsが存在するを確認します。1 つは Microsoft Cloud Deutschland 用、もう 1 つはグローバル Office 365サービス用です。</span><span class="sxs-lookup"><span data-stu-id="114ec-146">Verify that two Relying PartyTtrusts are present; one for Microsoft Cloud Deutschland and one for the Office 365 Global service.</span></span> <span data-ttu-id="114ec-147">次のコマンドをチェックに活用できます。</span><span class="sxs-lookup"><span data-stu-id="114ec-147">The following command can be leveraged for the check.</span></span> <span data-ttu-id="114ec-148">2 つの行と、それぞれの名前と識別子を返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="114ec-148">It should return two rows and the respective names and identifiers.</span></span>

   ```powershell
   Get-AdfsRelyingPartyTrust | Where-Object {$_.Identifier -like 'urn:federation:MicrosoftOnline*'} | Select-Object Name, Identifier
   ```

4. <span data-ttu-id="114ec-149">次の手順を使用して、両方の証明書利用者信頼を含む完全な移行構成 [をバックアップします](#backup)。</span><span class="sxs-lookup"><span data-stu-id="114ec-149">Backup your full migration configuration, including both Relying Party trusts, using [these steps](#backup).</span></span> <span data-ttu-id="114ec-150">**MicrosoftCloudDeutschlandAndWorldwide という名前で保存します**。</span><span class="sxs-lookup"><span data-stu-id="114ec-150">Save it with the name **MicrosoftCloudDeutschlandAndWorldwide**.</span></span>

5. <span data-ttu-id="114ec-151">テナントの移行中に、サポートされているさまざまな移行手順で、AD FS 認証が Microsoft Cloud Deutschland および Microsoft Global クラウドで動作しているのを定期的に確認します。</span><span class="sxs-lookup"><span data-stu-id="114ec-151">While your tenant is in migration, regularly verify that AD FS authentication is working with Microsoft Cloud Deutschland and Microsoft Global cloud in the various supported migration steps.</span></span>

## <a name="ad-fs-disaster-recovery-wid-database"></a><span data-ttu-id="114ec-152">AD FS 障害復旧 (WID データベース)</span><span class="sxs-lookup"><span data-stu-id="114ec-152">AD FS Disaster Recovery (WID Database)</span></span>

<span data-ttu-id="114ec-153">障害時にAD FS ファームを復元するにはAD [FS Rapid Restore Tool](/windows-server/identity/ad-fs/operations/ad-fs-rapid-restore-tool) を活用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="114ec-153">To restore the AD FS farm in a disaster [AD FS Rapid Restore Tool](/windows-server/identity/ad-fs/operations/ad-fs-rapid-restore-tool) needs to be leveraged.</span></span> <span data-ttu-id="114ec-154">したがって、ツールをダウンロードし、移行の開始前にバックアップを作成して安全に保存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="114ec-154">Therefore, the tool must be downloaded and before the start of the migration a backup must be created and safely stored.</span></span> <span data-ttu-id="114ec-155">この例では、WID データベースで実行されているファームをバックアップするために、次のコマンドを実行しています。</span><span class="sxs-lookup"><span data-stu-id="114ec-155">In this example, the following commands have been run to back up a farm running on a WID database:</span></span>

<h2 id="backup"></h2>

### <a name="back-up-an-ad-fs-farm"></a><span data-ttu-id="114ec-156">FS ファームADバックアップする</span><span class="sxs-lookup"><span data-stu-id="114ec-156">Back up an AD FS Farm</span></span>

1. <span data-ttu-id="114ec-157">FS サーバー AD FS ラピッド 復元ツールをインストールADします。</span><span class="sxs-lookup"><span data-stu-id="114ec-157">Install the AD FS Rapid Restore Tool on the primary AD FS server.</span></span>

2. <span data-ttu-id="114ec-158">このコマンドを使用して、PowerShell セッションでモジュールをインポートします。</span><span class="sxs-lookup"><span data-stu-id="114ec-158">Import the module in a PowerShell session with this command.</span></span>

   ```powershell
   Import-Module "C:\Program Files (x86)\ADFS Rapid Recreation Tool\ADFSRapidRecreationTool.dll"
   ```

3. <span data-ttu-id="114ec-159">バックアップ コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="114ec-159">Run the backup command:</span></span>

   ```powershell
   Backup-ADFS -StorageType "FileSystem" -storagePath "<Storage path of backup>" -EncryptionPassword "<password>" -BackupComment "Restore Doku" -BackupDKM
   ```

4. <span data-ttu-id="114ec-160">バックアップを目的の宛先に安全に保存します。</span><span class="sxs-lookup"><span data-stu-id="114ec-160">Store the backup safely on a desired destination.</span></span>

### <a name="restore-an-ad-fs-farm"></a><span data-ttu-id="114ec-161">FS ファームAD復元する</span><span class="sxs-lookup"><span data-stu-id="114ec-161">Restore an AD FS Farm</span></span>

<span data-ttu-id="114ec-162">ファームが完全に失敗し、古いファームに戻る方法がない場合は、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="114ec-162">If your farm failed completely and there is no way to return to the old farm, do the following.</span></span> 

1. <span data-ttu-id="114ec-163">以前に生成され保存されたバックアップを FS サーバーの新しいプライマリ AD移動します。</span><span class="sxs-lookup"><span data-stu-id="114ec-163">Move the previously generated and stored backup to the new primary AD FS server.</span></span>

2. <span data-ttu-id="114ec-164">次の `Restore-ADFS` PowerShell コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="114ec-164">Run the following `Restore-ADFS` PowerShell command.</span></span> <span data-ttu-id="114ec-165">必要に応じて、事前AD FS SSL 証明書をインポートします。</span><span class="sxs-lookup"><span data-stu-id="114ec-165">If necessary, import the AD FS SSL certificate beforehand.</span></span>

   ```powershell
   Restore-ADFS -StorageType "FileSystem" -StoragePath "<Path to Backup>" -DecryptionPassword "<password>" -GroupServiceAccountIdentifier "<gMSA>" -DBConnectionString "WID" -RestoreDKM
   ```

3. <span data-ttu-id="114ec-166">新しい DNS レコードまたはロード バランサーを FS サーバーの新しいADポイントします。</span><span class="sxs-lookup"><span data-stu-id="114ec-166">Point your new DNS records or load balancer to the new AD FS servers.</span></span>

## <a name="more-information"></a><span data-ttu-id="114ec-167">詳細情報</span><span class="sxs-lookup"><span data-stu-id="114ec-167">More information</span></span>

<span data-ttu-id="114ec-168">はじめに:</span><span class="sxs-lookup"><span data-stu-id="114ec-168">Getting started:</span></span>

- [<span data-ttu-id="114ec-169">Microsoft Cloud Deutschland から新しいドイツのデータセンター地域Office 365サービスへの移行</span><span class="sxs-lookup"><span data-stu-id="114ec-169">Migration from Microsoft Cloud Deutschland to Office 365 services in the new German datacenter regions</span></span>](ms-cloud-germany-transition.md)
- [<span data-ttu-id="114ec-170">Microsoft Cloud Deutschland 移行アシスタント</span><span class="sxs-lookup"><span data-stu-id="114ec-170">Microsoft Cloud Deutschland Migration Assistance</span></span>](https://aka.ms/germanymigrateassist)
- [<span data-ttu-id="114ec-171">移行のオプトイン方法</span><span class="sxs-lookup"><span data-stu-id="114ec-171">How to opt-in for migration</span></span>](ms-cloud-germany-migration-opt-in.md)
- [<span data-ttu-id="114ec-172">移行中のカスタマー エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="114ec-172">Customer experience during the migration</span></span>](ms-cloud-germany-transition-experience.md)

<span data-ttu-id="114ec-173">切り替えの移動:</span><span class="sxs-lookup"><span data-stu-id="114ec-173">Moving through the transition:</span></span>

- [<span data-ttu-id="114ec-174">移行フェーズのアクションと影響</span><span class="sxs-lookup"><span data-stu-id="114ec-174">Migration phases actions and impacts</span></span>](ms-cloud-germany-transition-phases.md)
- [<span data-ttu-id="114ec-175">その他の作業前</span><span class="sxs-lookup"><span data-stu-id="114ec-175">Additional pre-work</span></span>](ms-cloud-germany-transition-add-pre-work.md)
- <span data-ttu-id="114ec-176">Azure [AD、デバイス](ms-cloud-germany-transition-add-devices.md)[、](ms-cloud-germany-transition-azure-ad.md)[エクスペリエンス](ms-cloud-germany-transition-add-experience.md)、および FS のAD[情報](ms-cloud-germany-transition-add-adfs.md)です。</span><span class="sxs-lookup"><span data-stu-id="114ec-176">Additional information for [Azure AD](ms-cloud-germany-transition-azure-ad.md), [devices](ms-cloud-germany-transition-add-devices.md), [experiences](ms-cloud-germany-transition-add-experience.md), and [AD FS](ms-cloud-germany-transition-add-adfs.md).</span></span>

<span data-ttu-id="114ec-177">クラウド アプリ:</span><span class="sxs-lookup"><span data-stu-id="114ec-177">Cloud apps:</span></span>

- [<span data-ttu-id="114ec-178">Dynamics 365 移行プログラム情報</span><span class="sxs-lookup"><span data-stu-id="114ec-178">Dynamics 365 migration program information</span></span>](/dynamics365/get-started/migrate-data-german-region)
- [<span data-ttu-id="114ec-179">Power BI 移行プログラム情報</span><span class="sxs-lookup"><span data-stu-id="114ec-179">Power BI migration program information</span></span>](/power-bi/admin/service-admin-migrate-data-germany)
- [<span data-ttu-id="114ec-180">Microsoft Teams へのアップグレードを開始する</span><span class="sxs-lookup"><span data-stu-id="114ec-180">Getting started with your Microsoft Teams upgrade</span></span>](/microsoftteams/upgrade-start-here)
