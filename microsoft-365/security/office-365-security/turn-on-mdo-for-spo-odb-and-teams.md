---
title: SharePoint、OneDrive、Microsoft Teams 用の ATP を有効にする
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.date: ''
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 07e76024-0c80-40dc-8c48-1dd0d0f863cb
ms.collection:
- M365-security-compliance
- SPO_Content
description: 管理者は、セーフ SharePoint、OneDrive、Microsoft Teams、Microsoft Teams の添付ファイルを有効にする方法について説明します。検出されたファイルのアラートを設定する方法も含まれます。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b64b3cfb29b3be999c9e26804e35dc4d02e48fbb
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/23/2021
ms.locfileid: "53083094"
---
# <a name="turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="7c0e4-103">SharePoint、OneDrive、Microsoft Teams 用の ATP を有効にする</span><span class="sxs-lookup"><span data-stu-id="7c0e4-103">Turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="7c0e4-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="7c0e4-104">**Applies to**</span></span>
- [<span data-ttu-id="7c0e4-105">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="7c0e4-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="7c0e4-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7c0e4-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="7c0e4-107">Microsoft Defender for Office 365、SharePoint、OneDrive、Microsoft Teamsファイルを誤って共有する組織を保護します。</span><span class="sxs-lookup"><span data-stu-id="7c0e4-107">Microsoft Defender for Office 365 for SharePoint, OneDrive, and Microsoft Teams protects your organization from inadvertently sharing malicious files.</span></span> <span data-ttu-id="7c0e4-108">詳細については、「[SharePoint、OneDrive、Microsoft Teams の安全な添付ファイル](mdo-for-spo-odb-and-teams.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7c0e4-108">For more information, see [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="7c0e4-109">この記事では、添付ファイルの有効化と構成セーフ、SharePoint、OneDrive、およびMicrosoft Teams。</span><span class="sxs-lookup"><span data-stu-id="7c0e4-109">This article contains the steps for enabling and configuring Safe Attachments for SharePoint, OneDrive, and Microsoft Teams.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="7c0e4-110">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="7c0e4-110">What do you need to know before you begin?</span></span>

- <span data-ttu-id="7c0e4-111"><https://security.microsoft.com> で Microsoft 365 Defender ポータルを開きます。</span><span class="sxs-lookup"><span data-stu-id="7c0e4-111">You open the Microsoft 365 Defender portal at <https://security.microsoft.com>.</span></span> <span data-ttu-id="7c0e4-112">[添付ファイル] ページに直接 **移動セーフ開** きます <https://security.microsoft.com/safeattachmentv2> 。</span><span class="sxs-lookup"><span data-stu-id="7c0e4-112">To go directly to the **Safe Attachments** page, open <https://security.microsoft.com/safeattachmentv2>.</span></span>

- <span data-ttu-id="7c0e4-113">SharePoint、OneDrive、および Microsoft Teams の添付ファイルを有効にするには、Microsoft 365 Defender ポータルの組織の管理またはセキュリティ管理者の役割グループのメンバーである必要があります。セーフ</span><span class="sxs-lookup"><span data-stu-id="7c0e4-113">To turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams, you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Microsoft 365 Defender portal.</span></span> <span data-ttu-id="7c0e4-114">詳細については、「[Microsoft 365 Defender ポータルのアクセス許可](permissions-microsoft-365-security-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7c0e4-114">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md).</span></span>

- <span data-ttu-id="7c0e4-115">SharePoint Online PowerShell を使用して悪意のあるファイルをダウンロードするユーザーを防ぐには、Azure [](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) AD のグローバル管理者または[SharePoint 管理者](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#sharepoint-administrator)の役割のメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="7c0e4-115">To use SharePoint Online PowerShell to prevent people from downloading malicious files, you need to be member of the [Global Administrator](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) or [SharePoint Administrator](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#sharepoint-administrator) roles in Azure AD.</span></span>

- <span data-ttu-id="7c0e4-116">組織で監査ログが有効になっているか確認します。</span><span class="sxs-lookup"><span data-stu-id="7c0e4-116">Verify that audit logging is enabled for your organization.</span></span> <span data-ttu-id="7c0e4-117">詳細については、「[監査ログの検索を有効または無効にする](../../compliance/turn-audit-log-search-on-or-off.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="7c0e4-117">For more information, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

- <span data-ttu-id="7c0e4-118">設定を有効にするには、最大 30 分かかります。</span><span class="sxs-lookup"><span data-stu-id="7c0e4-118">Allow up to 30 minutes for the settings to take effect.</span></span>

## <a name="step-1-use-the-microsoft-365-defender-portal-to-turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="7c0e4-119">手順 1: Microsoft 365 Defender ポータルを使用して、セーフ SharePoint、OneDrive、およびMicrosoft Teams</span><span class="sxs-lookup"><span data-stu-id="7c0e4-119">Step 1: Use the Microsoft 365 Defender portal to turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>

1. <span data-ttu-id="7c0e4-120">ポータルで、[Microsoft 365 Defenderのルールの脅威ポリシーポリシー  ] セクション&に移動し、[添付 \>  \>  \> **セーフします**。</span><span class="sxs-lookup"><span data-stu-id="7c0e4-120">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat policies** \> **Policies** section \> **Safe Attachments**.</span></span>

2. <span data-ttu-id="7c0e4-121">[添付ファイル **セーフ] ページで**、[グローバル設定]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="7c0e4-121">On the **Safe Attachments** page, click **Global settings**.</span></span>

3. <span data-ttu-id="7c0e4-122">表示される **[グローバル設定**] フライアウトで、[ファイルの保護] セクションSharePoint、OneDrive、Microsoft Teamsします。 </span><span class="sxs-lookup"><span data-stu-id="7c0e4-122">In the **Global settings** fly out that appears, go to the **Protect files in SharePoint, OneDrive, and Microsoft Teams** section.</span></span>

   <span data-ttu-id="7c0e4-123">**SharePoint、OneDrive、** および Microsoft Teams の Office 365 の Defender をオンに切り替え、SharePoint、OneDrive、および Microsoft Teams の セーフ 添付ファイルをオンにします。 ![ ](../../media/scc-toggle-on.png)</span><span class="sxs-lookup"><span data-stu-id="7c0e4-123">Move the **Turn on Defender for Office 365 for SharePoint, OneDrive, and Microsoft Teams** toggle to the right ![Toggle on](../../media/scc-toggle-on.png) to turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams.</span></span>

   <span data-ttu-id="7c0e4-124">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7c0e4-124">When you're finished, click **Save**.</span></span>

### <a name="use-exchange-online-powershell-to-turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="7c0e4-125">PowerShell Exchange Onlineを使用して、セーフ、SharePoint、OneDriveの添付ファイルMicrosoft Teams</span><span class="sxs-lookup"><span data-stu-id="7c0e4-125">Use Exchange Online PowerShell to turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>

<span data-ttu-id="7c0e4-126">SharePoint、OneDrive、および Microsoft Teams の セーフ 添付ファイルを有効にする場合は[、Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)に接続し、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="7c0e4-126">If you'd rather use PowerShell to turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) and run the following command:</span></span>

```powershell
Set-AtpPolicyForO365 -EnableATPForSPOTeamsODB $true
```

<span data-ttu-id="7c0e4-127">構文とパラメーターの詳細については [、「Set-AtpPolicyForO365」を参照してください](/powershell/module/exchange/set-atppolicyforo365)。</span><span class="sxs-lookup"><span data-stu-id="7c0e4-127">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365).</span></span>

## <a name="step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files"></a><span data-ttu-id="7c0e4-128">手順 2: (推奨) オンライン PowerShell SharePointを使用して、ユーザーが悪意のあるファイルをダウンロードすることを防止する</span><span class="sxs-lookup"><span data-stu-id="7c0e4-128">Step 2: (Recommended) Use SharePoint Online PowerShell to prevent users from downloading malicious files</span></span>

<span data-ttu-id="7c0e4-129">既定では、SharePoint、OneDrive、および Microsoft Teams の セーフ 添付ファイルによって検出された悪意のあるファイルを開く、移動、コピー、または共有 <sup>\*</sup> Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="7c0e4-129">By default, users can't open, move, copy, or share<sup>\*</sup> malicious files that are detected by Safe Attachments for SharePoint, OneDrive, and Microsoft Teams.</span></span> <span data-ttu-id="7c0e4-130">ただし、悪意のあるファイルを削除してダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="7c0e4-130">However, they can delete and download malicious files.</span></span>

<span data-ttu-id="7c0e4-131"><sup>\*</sup> ユーザーが [アクセスの管理 **] に移動** した場合でも、[ **共有** ] オプションは引き続き使用できます。</span><span class="sxs-lookup"><span data-stu-id="7c0e4-131"><sup>\*</sup> If users go to **Manage access**, the **Share** option is still available.</span></span>

<span data-ttu-id="7c0e4-132">ユーザーが悪意のあるファイルをダウンロードできない場合は、オンライン[powerShell SharePointに](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)接続し、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="7c0e4-132">To prevent users from downloading malicious files, [connect to SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) and run the following command:</span></span>

```powershell
Set-SPOTenant -DisallowInfectedFileDownload $true
```

<span data-ttu-id="7c0e4-133">**注**:</span><span class="sxs-lookup"><span data-stu-id="7c0e4-133">**Notes**:</span></span>

- <span data-ttu-id="7c0e4-134">この設定は、ユーザーと管理者の両方に影響します。</span><span class="sxs-lookup"><span data-stu-id="7c0e4-134">This setting affects both users and admins.</span></span>
- <span data-ttu-id="7c0e4-135">ユーザーは引き続き悪意のあるファイルを削除できます。</span><span class="sxs-lookup"><span data-stu-id="7c0e4-135">People can still delete malicious files.</span></span>

<span data-ttu-id="7c0e4-136">構文とパラメーターの詳細については [、「Set-SPOTenant」を参照してください](/powershell/module/sharepoint-online/Set-SPOTenant)。</span><span class="sxs-lookup"><span data-stu-id="7c0e4-136">For detailed syntax and parameter information, see [Set-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant).</span></span>

## <a name="step-3-recommended-use-the-microsoft-365-defender-portal-to-create-an-alert-policy-for-detected-files"></a><span data-ttu-id="7c0e4-137">手順 3 (推奨) Microsoft 365 Defenderを使用して、検出されたファイルのアラート ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="7c0e4-137">Step 3 (Recommended) Use the Microsoft 365 Defender portal to create an alert policy for detected files</span></span>

<span data-ttu-id="7c0e4-138">SharePoint、OneDrive、および Microsoft Teams の添付ファイルが悪意のあるファイルを検出したときに、セーフ 管理者に通知するアラート ポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="7c0e4-138">You can create an alert policy that notifies you and other admins when Safe Attachments for SharePoint, OneDrive, and Microsoft Teams detects a malicious file.</span></span> <span data-ttu-id="7c0e4-139">アラートの詳細については、「Create [activity alerts in the Microsoft 365 Defender ポータル」を参照してください](../../compliance/create-activity-alerts.md)。</span><span class="sxs-lookup"><span data-stu-id="7c0e4-139">To learn more about alerts, see [Create activity alerts in the Microsoft 365 Defender portal](../../compliance/create-activity-alerts.md).</span></span>

1. <span data-ttu-id="7c0e4-140">[ポリシー] Microsoft 365 Defenderに移動し、[ポリシー] **&** \> **ポリシーを** 開きます <https://security.microsoft.com/alertpolicies> 。</span><span class="sxs-lookup"><span data-stu-id="7c0e4-140">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Alert policy** or open <https://security.microsoft.com/alertpolicies>.</span></span>

2. <span data-ttu-id="7c0e4-141">[アラート ポリシー **] ページで** 、[新しいアラート ポリシー **] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="7c0e4-141">On the **Alert policy** page, click **New alert policy**.</span></span>

3. <span data-ttu-id="7c0e4-142">新 **しいアラート ポリシー ウィザード** がフライアウトで開きます。[アラートに **名前を付け] ページ** で、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="7c0e4-142">The **New alert policy** wizard opens in a fly out. On the **Name your alert** page, configure the following settings:</span></span>
   - <span data-ttu-id="7c0e4-143">**名前**: 一意でわかりやすい名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="7c0e4-143">**Name**: Type a unique and descriptive name.</span></span> <span data-ttu-id="7c0e4-144">たとえば、ライブラリ内の悪意のあるファイル。</span><span class="sxs-lookup"><span data-stu-id="7c0e4-144">For example, Malicious Files in Libraries.</span></span>
   - <span data-ttu-id="7c0e4-145">**説明**: オプションの説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="7c0e4-145">**Description**: Type an optional description.</span></span> <span data-ttu-id="7c0e4-146">たとえば、悪意のあるファイルがオンライン、SharePoint、またはOneDriveで検出Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="7c0e4-146">For example, Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams.</span></span>
   - <span data-ttu-id="7c0e4-147">**重大度 :** ドロップダウン リストから **[低\*\*\*\*]、[中**]、または [高] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7c0e4-147">**Severity**: Select **Low**, **Medium**, or **High** from the drop down list.</span></span>
   - <span data-ttu-id="7c0e4-148">**カテゴリ**: ドロップダウン **リストから [脅威** の管理] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7c0e4-148">**Category**: Select **Threat management** from the drop down list.</span></span>

   <span data-ttu-id="7c0e4-149">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7c0e4-149">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="7c0e4-150">[アラート設定 **の作成] ページ** で、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="7c0e4-150">On the **Create alert settings** page, configure the following settings:</span></span>
   - <span data-ttu-id="7c0e4-151">**何を通知しますか?** section \> **Activity is** \> Select **Detected malware in file from** the drop down list.</span><span class="sxs-lookup"><span data-stu-id="7c0e4-151">**What do you want to alert on?** section \> **Activity is** \> Select **Detected malware in file** from the drop down list.</span></span>
   - <span data-ttu-id="7c0e4-152">**アラートをトリガーする** 方法セクション: 既定値のままにする **アクティビティが選択したルールと一致する度** に指定します。</span><span class="sxs-lookup"><span data-stu-id="7c0e4-152">**How do you want the alert to be triggered?** section: Leave the default value **Every time an activity matches the rule** selected.</span></span>

   <span data-ttu-id="7c0e4-153">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7c0e4-153">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="7c0e4-154">[受信者 **の設定] ページで** 、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="7c0e4-154">On the **Set your recipients** page, configure the following settings:</span></span>
   - <span data-ttu-id="7c0e4-155">[電子 **メール通知の送信] が** 選択されているのを確認します。</span><span class="sxs-lookup"><span data-stu-id="7c0e4-155">Verify **Send email notifications** is selected.</span></span> <span data-ttu-id="7c0e4-156">[ **電子メールの受信者]** ボックスで、悪意のあるファイルが検出された場合に通知を受け取る必要がある 1 つ以上のグローバル管理者、セキュリティ管理者、またはセキュリティ リーダーを選択します。</span><span class="sxs-lookup"><span data-stu-id="7c0e4-156">In the **Email recipients** box, select one or more global administrators, security administrators, or security readers who should receive notification when a malicious file is detected.</span></span>
   - <span data-ttu-id="7c0e4-157">**1 日の通知** の制限 : 既定値 [制限 **なし] を** 選択のままにします。</span><span class="sxs-lookup"><span data-stu-id="7c0e4-157">**Daily notification limit**: Leave the default value **No limit** selected.</span></span>

   <span data-ttu-id="7c0e4-158">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7c0e4-158">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="7c0e4-159">[設定 **の確認] ページで** 、設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="7c0e4-159">On the **Review your settings** page, review your settings.</span></span> <span data-ttu-id="7c0e4-160">各セクションで **[編集]** を選択して、そのセクション内の設定を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="7c0e4-160">You can select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="7c0e4-161">または、**[戻る]** をクリックするか、ウィザードで特定のページを選択します。</span><span class="sxs-lookup"><span data-stu-id="7c0e4-161">Or you can click **Back** or select the specific page in the wizard.</span></span>

   <span data-ttu-id="7c0e4-162">[ポリシー **をすぐ有効** にしますか? ] セクションで、既定値 **は [は** い] のままにし、右クリックしてオンにしてください。</span><span class="sxs-lookup"><span data-stu-id="7c0e4-162">In the **Do you want to turn the policy on right away?** section, leave the default value **Yes, turn it on right away** selected.</span></span>

   <span data-ttu-id="7c0e4-163">完了したら、 **[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7c0e4-163">When you're finished, click **Finish**.</span></span>

### <a name="use-security--compliance-powershell-to-create-an-alert-policy-for-detected-files"></a><span data-ttu-id="7c0e4-164">セキュリティ ポリシー&コンプライアンス PowerShell を使用して、検出されたファイルのアラート ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="7c0e4-164">Use Security & Compliance PowerShell to create an alert policy for detected files</span></span>

<span data-ttu-id="7c0e4-165">前のセクションで説明したように、PowerShell を使用して同じアラート ポリシーを作成する場合は、セキュリティ & コンプライアンス センター [PowerShell](/powershell/exchange/connect-to-scc-powershell) に接続し、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="7c0e4-165">If you'd rather use PowerShell to create the same alert policy as described in the previous section, [connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) and run the following command:</span></span>

```powershell
New-ActivityAlert -Name "Malicious Files in Libraries" -Description "Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams" -Category ThreatManagement -Operation FileMalwareDetected -NotifyUser "admin1@contoso.com","admin2@contoso.com"
```

<span data-ttu-id="7c0e4-166">**注**: 既定の _重大度の値は_ 低です。</span><span class="sxs-lookup"><span data-stu-id="7c0e4-166">**Note**: The default _Severity_ value is Low.</span></span> <span data-ttu-id="7c0e4-167">中または高を指定するには、コマンドに _Severity_ パラメーターと値を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="7c0e4-167">To specify Medium or High, include the _Severity_ parameter and value in the command.</span></span>

<span data-ttu-id="7c0e4-168">構文とパラメーターの詳細については [、「New-ActivityAlert」を参照してください](/powershell/module/exchange/new-activityalert)。</span><span class="sxs-lookup"><span data-stu-id="7c0e4-168">For detailed syntax and parameter information, see [New-ActivityAlert](/powershell/module/exchange/new-activityalert).</span></span>

### <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="7c0e4-169">正常な動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="7c0e4-169">How do you know these procedures worked?</span></span>

- <span data-ttu-id="7c0e4-170">SharePoint、OneDrive、および Microsoft Teams の セーフ 添付ファイルが正常に有効になっていることを確認するには、次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="7c0e4-170">To verify that you've successfully turned on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams, use either of the following steps:</span></span>

  - <span data-ttu-id="7c0e4-171">Microsoft 365 Defender ポータルで、[ポリシー & **rules** Threat \>  \> **Policies Policies]** セクション \> **セーフ Attachments** に移動し、[グローバル設定] を選択し、[SharePoint、OneDrive、および Microsoft Teams の Office 365 の Defender を有効にする] 設定の値を確認します。</span><span class="sxs-lookup"><span data-stu-id="7c0e4-171">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Policies** section \> **Safe Attachments**, select **Global settings**, and verify the value of the **Turn on Defender for Office 365 for SharePoint, OneDrive, and Microsoft Teams** setting.</span></span>

  - <span data-ttu-id="7c0e4-172">PowerShell Exchange Onlineで、次のコマンドを実行してプロパティ設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="7c0e4-172">In Exchange Online PowerShell, run the following command to verify the property setting:</span></span>

    ```powershell
    Get-AtpPolicyForO365 | Format-List EnableATPForSPOTeamsODB
    ```

    <span data-ttu-id="7c0e4-173">構文とパラメーターの詳細については [、「Get-AtpPolicyForO365」を参照してください](/powershell/module/exchange/get-atppolicyforo365)。</span><span class="sxs-lookup"><span data-stu-id="7c0e4-173">For detailed syntax and parameter information, see [Get-AtpPolicyForO365](/powershell/module/exchange/get-atppolicyforo365).</span></span>

- <span data-ttu-id="7c0e4-174">悪意のあるファイルのダウンロードが正常にブロックされたことを確認するには、SharePoint Online PowerShell を開き、次のコマンドを実行してプロパティ値を確認します。</span><span class="sxs-lookup"><span data-stu-id="7c0e4-174">To verify that you've successfully blocked people from downloading malicious files, open SharePoint Online PowerShell, and run the following command to verify the property value:</span></span>

  ```powershell
  Get-SPOTenant | Format-List DisallowInfectedFileDownload
  ```

  <span data-ttu-id="7c0e4-175">構文とパラメーターの詳細については [、「Get-SPOTenant」を参照してください](/powershell/module/sharepoint-online/Set-SPOTenant)。</span><span class="sxs-lookup"><span data-stu-id="7c0e4-175">For detailed syntax and parameter information, see [Get-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant).</span></span>

- <span data-ttu-id="7c0e4-176">検出されたファイルのアラート ポリシーが正常に構成されたことを確認するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="7c0e4-176">To verify that you've successfully configured an alert policy for detected files, use any of the following steps:</span></span>
  - <span data-ttu-id="7c0e4-177">[ポリシー] Microsoft 365 Defenderに移動し、[ポリシー  ] &アラート ポリシーを選択し、 \>  \> 設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="7c0e4-177">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Alert policy** \> select the alert policy, and verify the settings.</span></span>
  - <span data-ttu-id="7c0e4-178">ポータル powerShell Microsoft 365 Defenderで、アラート ポリシーの名前に置き換え、次のコマンドを実行し、プロパティ \<AlertPolicyName\> 値を確認します。</span><span class="sxs-lookup"><span data-stu-id="7c0e4-178">In Microsoft 365 Defender portal PowerShell, replace \<AlertPolicyName\> with the name of the alert policy, run the following command, and verify the property values:</span></span>

    ```powershell
    Get-ActivityAlert -Identity "<AlertPolicyName>"
    ```

    <span data-ttu-id="7c0e4-179">構文とパラメーターの詳細については [、「Get-ActivityAlert」を参照してください](/powershell/module/exchange/get-activityalert)。</span><span class="sxs-lookup"><span data-stu-id="7c0e4-179">For detailed syntax and parameter information, see [Get-ActivityAlert](/powershell/module/exchange/get-activityalert).</span></span>

- <span data-ttu-id="7c0e4-180">脅威保護[の状態レポートを使用](view-email-security-reports.md#threat-protection-status-report)して、検出されたファイルに関する情報を、SharePoint、OneDrive、およびMicrosoft Teams。</span><span class="sxs-lookup"><span data-stu-id="7c0e4-180">Use the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report) to view information about detected files in SharePoint, OneDrive, and Microsoft Teams.</span></span> <span data-ttu-id="7c0e4-181">具体的には、[データの表示方法: コンテンツ マルウェア **] ビュー \> を使用** できます。</span><span class="sxs-lookup"><span data-stu-id="7c0e4-181">Specifically, you can use the **View data by: Content \> Malware** view.</span></span>
