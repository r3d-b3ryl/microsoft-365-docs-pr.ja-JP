---
title: Microsoft Cloud Deutschland からの移行の移行後のアクティビティ
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/11/2020
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
description: '概要: 移行後のアクティビティは、Microsoft Cloud Germany (Microsoft Cloud Deutschland) から新しいドイツのデータセンター地域Office 365サービスに移行した後です。'
ms.openlocfilehash: ee8dedf7ffaf6bfc4246b1a8cc2522c15d763cd1
ms.sourcegitcommit: 1c53f114a810e7aaa2dc876b84d66348492ea36c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2021
ms.locfileid: "51899366"
---
# <a name="post-migration-activities-for-the-migration-from-microsoft-cloud-deutschland"></a><span data-ttu-id="3a84f-103">Microsoft Cloud Deutschland からの移行の移行後のアクティビティ</span><span class="sxs-lookup"><span data-stu-id="3a84f-103">Post-migration activities for the migration from Microsoft Cloud Deutschland</span></span>

<span data-ttu-id="3a84f-104">次のセクションでは、Microsoft Cloud Germany (Microsoft Cloud Deutschland) から新しいドイツデータセンター地域の Office 365 サービスに移行した後、複数のサービスの移行後のアクティビティを提供します。</span><span class="sxs-lookup"><span data-stu-id="3a84f-104">The following sections provide post-migration activities for multiple services after moving from Microsoft Cloud Germany (Microsoft Cloud Deutschland) to Office 365 services in the new German datacenter region.</span></span>

## <a name="azure-ad"></a><span data-ttu-id="3a84f-105">Azure AD</span><span class="sxs-lookup"><span data-stu-id="3a84f-105">Azure AD</span></span>
<!-- This AAD Endpoints comparison table could be added to the documentation, not finally decided.
### Azure AD Endpoints
**Applies to:** All customers

After the cut over to Azure AD is complete, the organization is fully using Office 365 services and is no longer connected to Microsoft Cloud Deutschland and the endpoints cannot be used anymore. At this point, the customer needs to ensure that all applications are using the endpoints for the new German datacenter region.
The following table provides an overview about which endpoints will replace the previously used endpoints in Microsoft Cloud Germany (Microsoft Cloud Deutschland). 

|Endpoint in Microsoft Cloud Germany  |Endpoint in the new German datacenter region  |
|:---------|:---------|
|becws.microsoftonline.de<br>provisioningapi.microsoftonline.de |becws.microsoftonline.com<br>provisioningapi.microsoftonline.com |
|adminwebservice.microsoftonline.de |adminwebservice.microsoftonline.com |
|login.microsoftonline.de<br>logincert.microsoftonline.de<br>sts.microsoftonline.de |login.microsoftonline.com<br>login.windows.net<br>logincert.microsoftonline.com<br>accounts.accesscontrol.windows.net |
|enterpriseregistration.microsoftonline.de |enterpriseregistration.windows.net |
|graph.cloudapi.de |graph.windows.net |
|graph.microsoft.de |graph.microsoft.com |
|||
-->

### <a name="azure-ad-federated-authentication-with-ad-fs"></a><span data-ttu-id="3a84f-106">Azure AD FS とのフェデレーションAD認証</span><span class="sxs-lookup"><span data-stu-id="3a84f-106">Azure AD federated authentication with AD FS</span></span>
<span data-ttu-id="3a84f-107">**適用対象:** FS とのフェデレーション認証を使用AD顧客</span><span class="sxs-lookup"><span data-stu-id="3a84f-107">**Applies to:** All customers using federated authentication with AD FS</span></span>

| <span data-ttu-id="3a84f-108">Step(s)</span><span class="sxs-lookup"><span data-stu-id="3a84f-108">Step(s)</span></span> | <span data-ttu-id="3a84f-109">説明</span><span class="sxs-lookup"><span data-stu-id="3a84f-109">Description</span></span> | <span data-ttu-id="3a84f-110">影響</span><span class="sxs-lookup"><span data-stu-id="3a84f-110">Impact</span></span> |
|:-------|:-------|:-------|
| <span data-ttu-id="3a84f-111">Microsoft Cloud Deutschland および FS から証明書利用者の信頼AD削除します。</span><span class="sxs-lookup"><span data-stu-id="3a84f-111">Remove relying party trusts from Microsoft Cloud Deutschland AD FS.</span></span> | <span data-ttu-id="3a84f-112">Azure への切りADが完了すると、組織は Office 365 サービスを完全に使用し、Microsoft Cloud Deutschland に接続されなくなりました。</span><span class="sxs-lookup"><span data-stu-id="3a84f-112">After the cut-over to Azure AD is complete, the organization is fully using Office 365 services and is no longer connected to Microsoft Cloud Deutschland.</span></span> <span data-ttu-id="3a84f-113">この時点で、顧客は Microsoft Cloud Deutschland エンドポイントに対する証明書利用者の信頼を削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3a84f-113">At this point, the customer needs to remove the relying party trust to the Microsoft Cloud Deutschland endpoints.</span></span> <span data-ttu-id="3a84f-114">これは、Azure AD が ID プロバイダー (IdP) として活用されている場合にのみ、お客様のアプリケーションが Microsoft Cloud Deutschland エンドポイントをポイントしない場合にのみ実行できます。</span><span class="sxs-lookup"><span data-stu-id="3a84f-114">This can only be done when none of the customer's applications points to Microsoft Cloud Deutschland endpoints when Azure AD is leveraged as an Identity Provider (IdP).</span></span> | <span data-ttu-id="3a84f-115">フェデレーション認証組織</span><span class="sxs-lookup"><span data-stu-id="3a84f-115">Federated Authentication organizations</span></span> | <span data-ttu-id="3a84f-116">なし。</span><span class="sxs-lookup"><span data-stu-id="3a84f-116">None.</span></span> |
||||

<!--
    Question from ckinder
    The following paragraph is not clear
-->
### <a name="group-approvals"></a><span data-ttu-id="3a84f-117">グループの承認</span><span class="sxs-lookup"><span data-stu-id="3a84f-117">Group approvals</span></span>
<span data-ttu-id="3a84f-118">**適用対象:** 移行前の過去 30 日間に Azure AD承認要求が承認されなかったエンド ユーザー</span><span class="sxs-lookup"><span data-stu-id="3a84f-118">**Applies to:** End-users whose Azure AD group approval requests weren't approved in the last 30 days before migration</span></span> 

| <span data-ttu-id="3a84f-119">Step(s)</span><span class="sxs-lookup"><span data-stu-id="3a84f-119">Step(s)</span></span> | <span data-ttu-id="3a84f-120">説明</span><span class="sxs-lookup"><span data-stu-id="3a84f-120">Description</span></span> | <span data-ttu-id="3a84f-121">影響</span><span class="sxs-lookup"><span data-stu-id="3a84f-121">Impact</span></span> |
|:-------|:-------|:-------|
| <span data-ttu-id="3a84f-122">移行前の過去 30 日間に Azure AD グループに参加する要求は、元の要求が承認されなかった場合は、再度要求する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3a84f-122">Requests to join an Azure AD group in the last 30 days before migration will need to be requested again if the original request wasn't approved.</span></span> | <span data-ttu-id="3a84f-123">移行前の過去 30 日間にこれらの要求が承認されなかった場合、エンドユーザーのお客様は Access パネルを使用して Azure AD グループに再度参加する要求を送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3a84f-123">End-user customers will need to use the Access panel to submit a request to join an Azure AD group again if those requests weren't approved in the last 30 days before the migration.</span></span> |  <span data-ttu-id="3a84f-124">エンド ユーザーとして次の情報を使用します。</span><span class="sxs-lookup"><span data-stu-id="3a84f-124">As an end-user:</span></span> <ol><li><span data-ttu-id="3a84f-125">[アクセス] [パネルに移動します](https://account.activedirectory.windowsazure.com/r#/joinGroups)。</span><span class="sxs-lookup"><span data-stu-id="3a84f-125">Navigate to [Access panel](https://account.activedirectory.windowsazure.com/r#/joinGroups).</span></span></li><li><span data-ttu-id="3a84f-126">移行前 30 ADの間にメンバーシップの承認が保留された Azure ユーザー グループを検索します。</span><span class="sxs-lookup"><span data-stu-id="3a84f-126">Find an Azure AD group for which membership approval was pending during the 30 days before migration.</span></span></li><li><span data-ttu-id="3a84f-127">Azure ADへの参加を要求します。</span><span class="sxs-lookup"><span data-stu-id="3a84f-127">Request to join the Azure AD group again.</span></span></li></ol> <span data-ttu-id="3a84f-128">移行の 30 日未満前にアクティブなグループに参加する要求は、移行後に再度要求されていない限り、承認できません。</span><span class="sxs-lookup"><span data-stu-id="3a84f-128">Requests to join a group that are active less than 30 days before migration cannot be approved, unless they're requested again after migration.</span></span> |
||||

<!--
    Question from ckinder
    The following paragraph is not clear
-->
## <a name="custom-dns-updates"></a><span data-ttu-id="3a84f-129">カスタム DNS 更新プログラム</span><span class="sxs-lookup"><span data-stu-id="3a84f-129">Custom DNS updates</span></span>
<span data-ttu-id="3a84f-130">**適用対象:**  自分の DNS ゾーンを管理しているすべての顧客</span><span class="sxs-lookup"><span data-stu-id="3a84f-130">**Applies to:**  All customer managing their own DNS zones</span></span>

| <span data-ttu-id="3a84f-131">Step(s)</span><span class="sxs-lookup"><span data-stu-id="3a84f-131">Step(s)</span></span> | <span data-ttu-id="3a84f-132">説明</span><span class="sxs-lookup"><span data-stu-id="3a84f-132">Description</span></span> | <span data-ttu-id="3a84f-133">影響</span><span class="sxs-lookup"><span data-stu-id="3a84f-133">Impact</span></span> |
|:------|:-------|:-------|
| <span data-ttu-id="3a84f-134">サービス エンドポイントのオンプレミス DNS サービスOffice 365更新します。</span><span class="sxs-lookup"><span data-stu-id="3a84f-134">Update on-premises DNS services for Office 365 services endpoints.</span></span> | <span data-ttu-id="3a84f-135">Microsoft Cloud Deutschland を指す顧客管理 DNS エントリは、グローバル サービス エンドポイントをポイントOffice 365更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3a84f-135">Customer-managed DNS entries that point to Microsoft Cloud Deutschland need to be updated to point to the Office 365 Global services endpoints.</span></span> | <span data-ttu-id="3a84f-136">サービスまたはソフトウェア クライアントの障害が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3a84f-136">Failure to do so may result in failure of the service or of software clients.</span></span> |
||||

## <a name="third-party-services"></a><span data-ttu-id="3a84f-137">サード パーティのサービス</span><span class="sxs-lookup"><span data-stu-id="3a84f-137">Third-party services</span></span>
<span data-ttu-id="3a84f-138">**適用対象:** サービス エンドポイントにサードパーティ サービスを使用Office 365顧客</span><span class="sxs-lookup"><span data-stu-id="3a84f-138">**Applies to:** Customers using third-party services for Office 365 services endpoints</span></span>

| <span data-ttu-id="3a84f-139">Step(s)</span><span class="sxs-lookup"><span data-stu-id="3a84f-139">Step(s)</span></span> | <span data-ttu-id="3a84f-140">説明</span><span class="sxs-lookup"><span data-stu-id="3a84f-140">Description</span></span> | <span data-ttu-id="3a84f-141">影響</span><span class="sxs-lookup"><span data-stu-id="3a84f-141">Impact</span></span> |
|:-------|:-------|:-------|
| <span data-ttu-id="3a84f-142">パートナーとサード パーティのサービスを、Office 365エンドポイントに更新します。</span><span class="sxs-lookup"><span data-stu-id="3a84f-142">Update partners and third-party services for Office 365 services endpoints.</span></span> | <ul><li><span data-ttu-id="3a84f-143">ドイツを指すサードパーティのサービスOffice 365パートナーは、サービス エンドポイントをポイントOffice 365する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3a84f-143">Third-party services and partners that point to Office 365 Germany need to be updated to point to the Office 365 services endpoints.</span></span> <span data-ttu-id="3a84f-144">例: 利用可能な場合は、ベンダーやパートナーと連携して、ギャラリー アプリのバージョンのアプリケーションを再登録します。</span><span class="sxs-lookup"><span data-stu-id="3a84f-144">Example: Re-register, in alignment with your vendors and partners, the gallery app version of applications, if available.</span></span> </li><li><span data-ttu-id="3a84f-145">API を利用するカスタム アプリケーションGraphをポイント `graph.microsoft.de` します `graph.microsoft.com` 。</span><span class="sxs-lookup"><span data-stu-id="3a84f-145">Point all custom applications that leverage Graph API from `graph.microsoft.de` to `graph.microsoft.com`.</span></span> <span data-ttu-id="3a84f-146">エンドポイントが変更された他の API も、活用する場合は更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3a84f-146">Other APIs with changed endpoints also need to be updated, if leveraged.</span></span> </li><li><span data-ttu-id="3a84f-147">すべてのファースト パーティ以外のエンタープライズ アプリケーションを変更して、世界中のエンドポイントにリダイレクトします。</span><span class="sxs-lookup"><span data-stu-id="3a84f-147">Change all non-first-party enterprise applications to redirect to the worldwide endpoints.</span></span> </li></ul>| <span data-ttu-id="3a84f-148">必須のアクション。</span><span class="sxs-lookup"><span data-stu-id="3a84f-148">Required action.</span></span> <span data-ttu-id="3a84f-149">サービスまたはソフトウェア クライアントの障害が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3a84f-149">Failure to do so may result in failure of the service or of software clients.</span></span> |
||||

## <a name="sharepoint-online"></a><span data-ttu-id="3a84f-150">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="3a84f-150">SharePoint Online</span></span>
<span data-ttu-id="3a84f-151">**適用対象**: 2013 ワークフロー SharePoint使用しているお客様</span><span class="sxs-lookup"><span data-stu-id="3a84f-151">**Applies to**: Customers using SharePoint 2013 Workflows</span></span>

| <span data-ttu-id="3a84f-152">Step(s)</span><span class="sxs-lookup"><span data-stu-id="3a84f-152">Step(s)</span></span> | <span data-ttu-id="3a84f-153">説明</span><span class="sxs-lookup"><span data-stu-id="3a84f-153">Description</span></span> | <span data-ttu-id="3a84f-154">影響</span><span class="sxs-lookup"><span data-stu-id="3a84f-154">Impact</span></span> |
|:-------|:-------|:-------|
| <span data-ttu-id="3a84f-155">2013 SharePointを再発行します。</span><span class="sxs-lookup"><span data-stu-id="3a84f-155">Republish SharePoint 2013 workflows.</span></span> | <span data-ttu-id="3a84f-156">移行前の作業では、2013 年のワークフロー SharePoint減らしました。</span><span class="sxs-lookup"><span data-stu-id="3a84f-156">In the pre-migration work, we reduced the number of SharePoint 2013 workflows.</span></span> <span data-ttu-id="3a84f-157">移行が完了すると、顧客はワークフローを再発行できます。</span><span class="sxs-lookup"><span data-stu-id="3a84f-157">Now with migration complete, the customer can republish the workflows.</span></span> | <span data-ttu-id="3a84f-158">これは必須のアクションです。</span><span class="sxs-lookup"><span data-stu-id="3a84f-158">This is a required action.</span></span> <span data-ttu-id="3a84f-159">そうしない場合は、ユーザーの混乱やヘルプ デスクの呼び出しが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3a84f-159">Failure to do so may result in user confusion and help desk calls.</span></span> |
| <span data-ttu-id="3a84f-160">アイテムを共有するには、Outlook</span><span class="sxs-lookup"><span data-stu-id="3a84f-160">Share items via Outlook</span></span> | <span data-ttu-id="3a84f-161">テナントの切りSharePoint後 OneDrive for Business、SharePoint経由Outlookアイテムの共有が機能しなくなりました。</span><span class="sxs-lookup"><span data-stu-id="3a84f-161">Sharing items in SharePoint Online and OneDrive for Business via Outlook no longer works after tenant cutover.</span></span> |<ul><li><span data-ttu-id="3a84f-162">[SharePoint]および [OneDrive for Business] では、アイテムを [オンライン] または [Outlook] で共有Outlook。</span><span class="sxs-lookup"><span data-stu-id="3a84f-162">In SharePoint Online and OneDrive for Business, you can share items via Outlook.</span></span> <span data-ttu-id="3a84f-163">[リンク] ボタンOutlookすると、共有可能なリンクが作成され、新しいメッセージにプッシュOutlook Web App。</span><span class="sxs-lookup"><span data-stu-id="3a84f-163">After pressing the Outlook button, a shareable link is created and pushed into a new message in the Outlook Web App.</span></span></li><li><span data-ttu-id="3a84f-164">テナントの切り替え後、この共有方法は機能しません。</span><span class="sxs-lookup"><span data-stu-id="3a84f-164">After tenant cutover, this method of sharing won't work.</span></span> <span data-ttu-id="3a84f-165">これは既知の問題だと認識しています。</span><span class="sxs-lookup"><span data-stu-id="3a84f-165">We recognize this is a known issue.</span></span> <span data-ttu-id="3a84f-166">ただし、このOutlook機能は廃止の道にあるので、廃止が展開されるまで問題の修正は計画されていません。</span><span class="sxs-lookup"><span data-stu-id="3a84f-166">However, since this Outlook feature is in the path of deprecation, fixing the issue is not planned until the deprecation is rolled out.</span></span> </li></ul>|
||||

## <a name="exchange-online"></a><span data-ttu-id="3a84f-167">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="3a84f-167">Exchange Online</span></span>
<span data-ttu-id="3a84f-168">**適用対象**: ハイブリッド 構成を使用しているExchangeします。</span><span class="sxs-lookup"><span data-stu-id="3a84f-168">**Applies to**: Customers using a hybrid Exchange configuration</span></span>

| <span data-ttu-id="3a84f-169">Step(s)</span><span class="sxs-lookup"><span data-stu-id="3a84f-169">Step(s)</span></span> | <span data-ttu-id="3a84f-170">説明</span><span class="sxs-lookup"><span data-stu-id="3a84f-170">Description</span></span> | <span data-ttu-id="3a84f-171">影響</span><span class="sxs-lookup"><span data-stu-id="3a84f-171">Impact</span></span> |
|:-------|:-------|:-------|
| <span data-ttu-id="3a84f-172">ハイブリッド構成ウィザード (HCW) を実行し、Office 365します。</span><span class="sxs-lookup"><span data-stu-id="3a84f-172">Rerun Hybrid Configuration wizard (HCW) against Office 365 services.</span></span> | <span data-ttu-id="3a84f-173">既存の HCW 構成は、Microsoft Cloud Deutschland をサポートすることを意図しています。</span><span class="sxs-lookup"><span data-stu-id="3a84f-173">The existing HCW configuration is meant to support Microsoft Cloud Deutschland.</span></span> <span data-ttu-id="3a84f-174">サービスの移行Exchange、Microsoft Cloud Deutschland からオンプレミス構成を切り離します。</span><span class="sxs-lookup"><span data-stu-id="3a84f-174">With migration of Exchange services complete, we decouple on-premises configuration from Microsoft Cloud Deutschland.</span></span> |<ul><li><span data-ttu-id="3a84f-175">必須のアクション。</span><span class="sxs-lookup"><span data-stu-id="3a84f-175">Required action.</span></span> <span data-ttu-id="3a84f-176">サービスまたはソフトウェア クライアントの障害が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3a84f-176">Failure to do so may result in failure of the service or of software clients.</span></span> <span data-ttu-id="3a84f-177">メールボックスExchange移行を開始する前に (5 日以上の通知を含む)、メールボックスのオンボーディングまたはオフボードの移動を停止して削除する必要があるクライアントに通知します。</span><span class="sxs-lookup"><span data-stu-id="3a84f-177">Before Exchange mailbox migration begins (with 5 or more days of notice), notify clients that they should stop and delete any onboarding or offboarding moves of their mailboxes.</span></span>  <span data-ttu-id="3a84f-178">表示しない場合は、移動要求にエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3a84f-178">If they don't, they'll see errors in their move requests.</span></span> </li><li><span data-ttu-id="3a84f-179">メールボックスExchangeが完了したら、オンボーディングとオフボードの移動を再開できるクライアントに通知します。</span><span class="sxs-lookup"><span data-stu-id="3a84f-179">After Exchange mailbox migration is complete, notify clients that they can resume onboarding and offboarding moves.</span></span> <br> <span data-ttu-id="3a84f-180">Microsoft Cloud Deutschland から Office 365 サービスへの Exchange の移行中に、PowerShell コマンドレットである **Test-MigrationServerAvailabiilty** を実行すると、動作しない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3a84f-180">Running **Test-MigrationServerAvailabiilty**, a PowerShell cmdlet, during migration of Exchange from Microsoft Cloud Deutschland to Office 365 services might not work.</span></span> <span data-ttu-id="3a84f-181">ただし、移行が完了すると正しく動作します。</span><span class="sxs-lookup"><span data-stu-id="3a84f-181">However, it will work properly after migration is complete.</span></span> </li><li><span data-ttu-id="3a84f-182">クライアントがメールボックスの移行後に資格情報または承認に関する問題にぶつかった場合、ユーザーは、Exchange コントロール パネル (ECP) を使用して、移行エンドポイントでオンプレミスの管理者資格情報を再入力できます。 `Set-MigrationEndpoint endpointName -Credential $(Get-Credential)`</span><span class="sxs-lookup"><span data-stu-id="3a84f-182">If clients run into issues with credentials or authorization after mailboxes are migrated, users can reenter their on-premises administrator credentials in the migration endpoint by running `Set-MigrationEndpoint endpointName -Credential $(Get-Credential)`, or by setting the same by using Exchange Control Panel (ECP).</span></span> </li></ul>|
