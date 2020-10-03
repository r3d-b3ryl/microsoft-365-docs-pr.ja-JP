---
title: Office 365 の ATP-SharePoint、OneDrive、& Teams をオンにする
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 07e76024-0c80-40dc-8c48-1dd0d0f863cb
ms.collection:
- M365-security-compliance
- SPO_Content
description: 検出されたファイルに対して通知を設定する方法など、SharePoint、OneDrive、Teams の ATP を有効にする方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0c717a89492ea1160f26f26f13be6c36f348c79c
ms.sourcegitcommit: 3a0accd616ca94d6ba7f50e502552b45e9661a95
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/03/2020
ms.locfileid: "48350657"
---
# <a name="turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="6325c-103">SharePoint、OneDrive、Microsoft Teams 用の ATP を有効にする</span><span class="sxs-lookup"><span data-stu-id="6325c-103">Turn on ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="6325c-104">Office 365 Advanced Threat Protection (ATP) for SharePoint、OneDrive、Microsoft Teams は、悪意のあるファイルを誤って共有することから組織を保護します。</span><span class="sxs-lookup"><span data-stu-id="6325c-104">Office 365 Advanced Threat Protection (ATP) for SharePoint, OneDrive, and Microsoft Teams protects your organization from inadvertently sharing malicious files.</span></span> <span data-ttu-id="6325c-105">詳細については、「 [SharePoint、OneDrive、Microsoft Teams 用の ATP](atp-for-spo-odb-and-teams.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6325c-105">For more information, see [ATP for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="6325c-106">この記事には、SharePoint、OneDrive、Microsoft Teams 用の ATP を有効にして構成するための手順が含まれています。</span><span class="sxs-lookup"><span data-stu-id="6325c-106">This article contains the steps for enabling and configuring ATP for SharePoint, OneDrive, and Microsoft Teams.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="6325c-107">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="6325c-107">What do you need to know before you begin?</span></span>

- <span data-ttu-id="6325c-108"><https://protection.office.com> でセキュリティ/コンプライアンス センターを開きます。</span><span class="sxs-lookup"><span data-stu-id="6325c-108">You open the Security & Compliance Center at <https://protection.office.com>.</span></span> <span data-ttu-id="6325c-109">[ATP の安全な **添付ファイル** ] ページに直接移動するには、を開き <https://protection.office.com/safeattachmentv2> ます。</span><span class="sxs-lookup"><span data-stu-id="6325c-109">To go directly to the **ATP Safe Attachments** page, open <https://protection.office.com/safeattachmentv2>.</span></span>

- <span data-ttu-id="6325c-110">SharePoint、OneDrive、Microsoft Teams 用の ATP を有効にするには、セキュリティ & コンプライアンスセンターの [ **組織の管理** ] または [ **セキュリティ管理者** ] の役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="6325c-110">To turn on ATP for SharePoint, OneDrive, and Microsoft Teams, you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="6325c-111">詳細については、「[セキュリティ/コンプライアンス センターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6325c-111">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="6325c-112">SharePoint Online の PowerShell を使用して、悪意のあるファイルがダウンロードされないようにするには、Azure AD の [全体管理者](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) または [sharepoint 管理者](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#sharepoint-administrator) ロールのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="6325c-112">To use SharePoint Online PowerShell to prevent people from downloading malicious files, you need to be member of the [Global Administrator](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) or [SharePoint Administrator](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#sharepoint-administrator) roles in Azure AD.</span></span>

- <span data-ttu-id="6325c-113">組織の監査ログが有効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="6325c-113">Verify that audit logging is enabled for your organization.</span></span> <span data-ttu-id="6325c-114">詳細については、「[監査ログの検索を有効または無効にする](../../compliance/turn-audit-log-search-on-or-off.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="6325c-114">For more information, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

- <span data-ttu-id="6325c-115">設定が有効になるまで最大30分間待ちます。</span><span class="sxs-lookup"><span data-stu-id="6325c-115">Allow up to 30 minutes for the settings to take effect.</span></span>

## <a name="step-1-use-the-security--compliance-center-to-turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="6325c-116">手順 1: セキュリティ & コンプライアンスセンターを使用して、SharePoint、OneDrive、Microsoft Teams 用の ATP を有効にする</span><span class="sxs-lookup"><span data-stu-id="6325c-116">Step 1: Use the Security & Compliance Center to turn on ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

1. <span data-ttu-id="6325c-117">セキュリティ & コンプライアンスセンターで、[ **脅威管理** \> **ポリシー** \> **ATP 安全添付ファイル**] に移動し、[ **グローバル設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6325c-117">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**, and click **Global settings**.</span></span>

2. <span data-ttu-id="6325c-118">[ **グローバル設定** ] が表示されたら、 **[SharePoint、OneDrive、MICROSOFT Teams の ATP を有効** にする] 設定に移動します。</span><span class="sxs-lookup"><span data-stu-id="6325c-118">In the **Global settings** fly out that appears, go to the **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams** setting.</span></span> <span data-ttu-id="6325c-119">右にトグルをオンにして、 ![ ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) SharePoint、OneDrive、Microsoft Teams 用の ATP を有効にします。</span><span class="sxs-lookup"><span data-stu-id="6325c-119">Move the toggle to the right ![Toggle on](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) to turn on ATP for SharePoint, OneDrive, and Microsoft Teams.</span></span>

   <span data-ttu-id="6325c-120">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6325c-120">When you're finished, click **Save**.</span></span>

### <a name="use-exchange-online-powershell-to-turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="6325c-121">Exchange Online の PowerShell を使用して、SharePoint、OneDrive、Microsoft Teams 用の ATP を有効にする</span><span class="sxs-lookup"><span data-stu-id="6325c-121">Use Exchange Online PowerShell to turn on ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

<span data-ttu-id="6325c-122">PowerShell を使用して、SharePoint、OneDrive、Microsoft Teams 用の ATP を有効にする場合は、 [Exchange Online PowerShell に接続](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) して次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="6325c-122">If you'd rather use PowerShell to turn on ATP for SharePoint, OneDrive, and Microsoft Teams, [connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) and run the following command:</span></span>

```powershell
Set-AtpPolicyForO365 -EnableATPForSPOTeamsODB $true
```

<span data-ttu-id="6325c-123">構文およびパラメーターの詳細については、「 [AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6325c-123">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).</span></span>

## <a name="step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files"></a><span data-ttu-id="6325c-124">手順 2: (推奨) SharePoint Online PowerShell を使用して、ユーザーが悪意のあるファイルをダウンロードできないようにする</span><span class="sxs-lookup"><span data-stu-id="6325c-124">Step 2: (Recommended) Use SharePoint Online PowerShell to prevent users from downloading malicious files</span></span>

<span data-ttu-id="6325c-125">既定では、ユーザーは ATP によって検出された悪意のあるファイルを開く、移動、コピー、または共有することはできません。</span><span class="sxs-lookup"><span data-stu-id="6325c-125">By default, users can't open, move, copy, or share malicious files that are detected by ATP.</span></span> <span data-ttu-id="6325c-126">ただし、悪意のあるファイルを削除してダウンロードすることはできます。</span><span class="sxs-lookup"><span data-stu-id="6325c-126">However, they can delete and download malicious files.</span></span>

<span data-ttu-id="6325c-127">ユーザーが悪意のあるファイルをダウンロードできないようにするには、 [SharePoint Online PowerShell に接続](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) し、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="6325c-127">To prevent users from downloading malicious files, [connect to SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) and run the following command:</span></span>

```powershell
Set-SPOTenant -DisallowInfectedFileDownload $true
```

<span data-ttu-id="6325c-128">**注**:</span><span class="sxs-lookup"><span data-stu-id="6325c-128">**Notes**:</span></span>

- <span data-ttu-id="6325c-129">この設定は、ユーザーと管理者の両方に影響します。</span><span class="sxs-lookup"><span data-stu-id="6325c-129">This setting affects both users and admins.</span></span>
- <span data-ttu-id="6325c-130">ユーザーは悪意のあるファイルを削除できます。</span><span class="sxs-lookup"><span data-stu-id="6325c-130">People can still delete malicious files.</span></span>

<span data-ttu-id="6325c-131">構文およびパラメーターの詳細については、「 [set-spotenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6325c-131">For detailed syntax and parameter information, see [Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant).</span></span>

## <a name="step-3-recommended-use-the-security--compliance-center-to-create-an-alert-policy-for-detected-files"></a><span data-ttu-id="6325c-132">手順 3 (推奨) セキュリティ & コンプライアンスセンターを使用して、検出されたファイルの通知ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="6325c-132">Step 3 (Recommended) Use the Security & Compliance Center to create an alert policy for detected files</span></span>

<span data-ttu-id="6325c-133">SharePoint、OneDrive、Microsoft Teams 用の ATP が悪意のあるファイルを検出したときに通知する通知ポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="6325c-133">You can create an alert policy that notifies you and other admins when ATP for SharePoint, OneDrive, and Microsoft Teams detects a malicious file.</span></span> <span data-ttu-id="6325c-134">通知の詳細については、「 [セキュリティ & コンプライアンスセンターでアクティビティ警告を作成](../../compliance/create-activity-alerts.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6325c-134">To learn more about alerts, see [Create activity alerts in the Security & Compliance Center](../../compliance/create-activity-alerts.md).</span></span>

1. <span data-ttu-id="6325c-135">[ [セキュリティ & コンプライアンスセンター](https://protection.office.com)] で、[ **alerts** \> **Alert policies** ] または [open] に移動し <https://protection.office.com/alertpolicies> ます。</span><span class="sxs-lookup"><span data-stu-id="6325c-135">In the [Security & Compliance Center](https://protection.office.com), go to **Alerts** \> **Alert policies** or open <https://protection.office.com/alertpolicies>.</span></span>

2. <span data-ttu-id="6325c-136">[ **通知ポリシー** ] ページで、[ **新しいアラートポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6325c-136">On the **Alert policies** page, click **New alert policy**.</span></span>

3. <span data-ttu-id="6325c-137">**新しい通知ポリシー**ウィザードがフライアウトで開きます。[**通知の名前**を指定してください] ページで、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="6325c-137">The **New alert policy** wizard opens in a fly out. On the **Name your alert** page, configure the following settings:</span></span>

   - <span data-ttu-id="6325c-138">[**名前**]: わかりやすい一意の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="6325c-138">**Name**: Type a unique and descriptive name.</span></span> <span data-ttu-id="6325c-139">たとえば、ライブラリ内の悪意のあるファイル。</span><span class="sxs-lookup"><span data-stu-id="6325c-139">For example, Malicious Files in Libraries.</span></span>
   - <span data-ttu-id="6325c-140">**説明**: 省略可能な説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="6325c-140">**Description**: Type an optional description.</span></span> <span data-ttu-id="6325c-141">たとえば、SharePoint Online、OneDrive、Microsoft Teams で悪意のあるファイルが検出されたときに管理者に通知します。</span><span class="sxs-lookup"><span data-stu-id="6325c-141">For example, Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams.</span></span>
   - <span data-ttu-id="6325c-142">**重要度**: 既定値の [ **低** ] を選択したままにするか、[ **中** ] または [ **高**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6325c-142">**Severity**: Leave the default value **Low** selected, or select **Medium** or **High**.</span></span>
   - <span data-ttu-id="6325c-143">**カテゴリを選択**します。 [ **脅威管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6325c-143">**Select a category**: Select **Threat management**.</span></span>

   <span data-ttu-id="6325c-144">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6325c-144">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="6325c-145">[ **通知設定の作成** ] ページで、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="6325c-145">On the **Create alert settings** page, configure the following settings:</span></span>

   - <span data-ttu-id="6325c-146">通知対象を選択してください。**アクティビティは**次のとおりです。 [**ファイルに検出されたマルウェア**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6325c-146">**What do you want to alert on?: Activity is**: Select **Detected malware in file**.</span></span>
   - <span data-ttu-id="6325c-147">**通知をどのようにトリガーしますか?**: アクティビティが選択した **ルールと一致** するたびに、既定値をそのまま使用します。</span><span class="sxs-lookup"><span data-stu-id="6325c-147">**How do you want the alert to be triggered?**: Leave the default value **Every time an activity matches the rule** selected.</span></span>

   <span data-ttu-id="6325c-148">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6325c-148">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="6325c-149">[ **受信者の設定** ] ページで、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="6325c-149">On the **Set your recipients** page, configure the following settings:</span></span>

   - <span data-ttu-id="6325c-150">**電子メール通知の送信**: この設定が選択されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="6325c-150">**Send email notifications**: Verify this setting is selected.</span></span> <span data-ttu-id="6325c-151">[ **電子メールの宛先** ] ボックスで、悪意のあるファイルが検出されたときに通知を受信する必要がある1人以上のグローバル管理者、セキュリティ管理者、またはセキュリティ閲覧者を選択します。</span><span class="sxs-lookup"><span data-stu-id="6325c-151">In the **Email recipients** box, select one or more global administrators, security administrators, or security readers who should receive notification when a malicious file is detected.</span></span>
   - <span data-ttu-id="6325c-152">[**毎日の通知制限数**: 既定値のままにします。 (**制限なし**)。</span><span class="sxs-lookup"><span data-stu-id="6325c-152">**Daily notification limit**: Leave the default value **No limit** selected.</span></span>

   <span data-ttu-id="6325c-153">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6325c-153">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="6325c-154">[ **設定の確認** ] ページで設定を確認し、いずれかのセクションの [ **編集** ] をクリックして変更を加えます。</span><span class="sxs-lookup"><span data-stu-id="6325c-154">On the **Review your settings** page, review the settings, and click **Edit** in any of the sections to make changes.</span></span>

   <span data-ttu-id="6325c-155">[ポリシーをすぐ **に有効** にしますか?] セクションで、既定値の **[はい] を** 選択し、[すぐにオン] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6325c-155">In the **Do you want to turn the policy on right away?** section, leave the default value **Yes, turn it on right away** selected.</span></span>

   <span data-ttu-id="6325c-156">完了したら、 **[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6325c-156">When you're finished, click **Finish**.</span></span>

### <a name="use-security--compliance-powershell-to-create-an-alert-policy-for-detected-files"></a><span data-ttu-id="6325c-157">セキュリティ & コンプライアンス PowerShell を使用して、検出されたファイルの通知ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="6325c-157">Use Security & Compliance PowerShell to create an alert policy for detected files</span></span>

<span data-ttu-id="6325c-158">PowerShell を使用して、前のセクションで説明したのと同じアラートポリシーを作成する場合は、「 [Security & コンプライアンスセンター PowerShell に接続](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) し、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="6325c-158">If you'd rather use PowerShell to create the same alert policy as described in the previous section, [connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) and run the following command:</span></span>

```powershell
New-ActivityAlert -Name "Malicious Files in Libraries" -Description "Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams" -Category ThreatManagement -Operation FileMalwareDetected -NotifyUser "admin1@contoso.com","admin2@contoso.com"
```

<span data-ttu-id="6325c-159">**注**: 既定の _重要度_ の値は低くなっています。</span><span class="sxs-lookup"><span data-stu-id="6325c-159">**Note**: The default _Severity_ value is Low.</span></span> <span data-ttu-id="6325c-160">中または高を指定するには、コマンドに _Severity_ パラメーターと値を含めます。</span><span class="sxs-lookup"><span data-stu-id="6325c-160">To specify Medium or High, include the _Severity_ parameter and value in the command.</span></span>

<span data-ttu-id="6325c-161">構文およびパラメーターの詳細については、「 [New-ActivityAlert](https://docs.microsoft.com/powershell/module/exchange/new-activityalert)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6325c-161">For detailed syntax and parameter information, see [New-ActivityAlert](https://docs.microsoft.com/powershell/module/exchange/new-activityalert).</span></span>

### <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="6325c-162">正常な動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="6325c-162">How do you know these procedures worked?</span></span>

- <span data-ttu-id="6325c-163">SharePoint、OneDrive、Microsoft Teams の ATP が正常に有効化されたことを確認するには、次のいずれかの手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="6325c-163">To verify that you've successfully turned on ATP for SharePoint, OneDrive, and Microsoft Teams, use either of the following steps:</span></span>

  - <span data-ttu-id="6325c-164">[セキュリティ & コンプライアンスセンター](https://protection.office.com)で、[脅威の**管理** \> **ポリシー]** \> ATP の [安全な**添付ファイル**] に移動し、[**グローバル設定**] を選択して、 **[SharePoint、OneDrive、および Microsoft Teams の**設定] の設定値を確認します。</span><span class="sxs-lookup"><span data-stu-id="6325c-164">In the [Security & Compliance Center](https://protection.office.com), go to **Threat management** \> **Policy** \> **ATP Safe Attachments**, select **Global settings**, and verify the value of the **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams** setting.</span></span>

  - <span data-ttu-id="6325c-165">Exchange Online PowerShell で次のコマンドを実行して、プロパティの設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="6325c-165">In Exchange Online PowerShell, run the following command to verify the property setting:</span></span>

    ```powershell
    Get-AtpPolicyForO365 | Format-List EnableATPForSPOTeamsODB
    ```

    <span data-ttu-id="6325c-166">構文およびパラメーターの詳細については、「 [AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/get-atppolicyforo365)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6325c-166">For detailed syntax and parameter information, see [Get-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/get-atppolicyforo365).</span></span>

- <span data-ttu-id="6325c-167">ユーザーが悪意のあるファイルをダウンロードできないようにしたことを確認するには、SharePoint Online PowerShell を開き、次のコマンドを実行してプロパティの値を確認します。</span><span class="sxs-lookup"><span data-stu-id="6325c-167">To verify that you've successfully blocked people from downloading malicious files, open SharePoint Online PowerShell, and run the following command to verify the property value:</span></span>

  ```powershell
  Get-SPOTenant | Format-List DisallowInfectedFileDownload
  ```

  <span data-ttu-id="6325c-168">構文およびパラメーターの詳細については、「 [set-spotenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6325c-168">For detailed syntax and parameter information, see [Get-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant).</span></span>

- <span data-ttu-id="6325c-169">検出されたファイルのアラートポリシーが正常に構成されたことを確認するには、次のいずれかの手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="6325c-169">To verify that you've successfully configured an alert policy for detected files, use any of the following steps:</span></span>

  - <span data-ttu-id="6325c-170">セキュリティ & コンプライアンスセンターで、[アラートの**アラート**ポリシー] に移動して \> **Alert policies** \> 通知ポリシーを選択し、設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="6325c-170">In the Security & Compliance Center, go to **Alerts** \> **Alert policies** \> select the alert policy, and verify the settings.</span></span>

  - <span data-ttu-id="6325c-171">セキュリティ & コンプライアンスセンターの PowerShell で、を \<AlertPolicyName\> アラートポリシーの名前に置き換え、次のコマンドを実行して、プロパティの値を確認します。</span><span class="sxs-lookup"><span data-stu-id="6325c-171">In Security & Compliance Center PowerShell, replace \<AlertPolicyName\> with the name of the alert policy, run the following command, and verify the property values:</span></span>

    ```powershell
    Get-ActivityAlert -Identity "<AlertPolicyName>"
    ```

    <span data-ttu-id="6325c-172">構文およびパラメーターの詳細については、「 [取得-ActivityAlert](https://docs.microsoft.com/powershell/module/exchange/get-activityalert)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6325c-172">For detailed syntax and parameter information, see [Get-ActivityAlert](https://docs.microsoft.com/powershell/module/exchange/get-activityalert).</span></span>

- <span data-ttu-id="6325c-173">[脅威保護の状態レポート](view-email-security-reports.md#threat-protection-status-report)を使用して、SharePoint、OneDrive、Microsoft Teams の検出されたファイルに関する情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="6325c-173">Use the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report) to view information about detected files in SharePoint, OneDrive, and Microsoft Teams.</span></span> <span data-ttu-id="6325c-174">具体的には、[ **データの表示方法: コンテンツ \> マルウェア** ] ビューを使用できます。</span><span class="sxs-lookup"><span data-stu-id="6325c-174">Specifically, you can use the **View data by: Content \> Malware** view.</span></span>
