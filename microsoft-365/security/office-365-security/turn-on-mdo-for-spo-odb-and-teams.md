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
ms.openlocfilehash: 374e67626eab07cc8ab89a52554658a31e661eec
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/14/2021
ms.locfileid: "52929949"
---
# <a name="turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="50f30-103">SharePoint、OneDrive、Microsoft Teams 用の ATP を有効にする</span><span class="sxs-lookup"><span data-stu-id="50f30-103">Turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="50f30-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="50f30-104">**Applies to**</span></span>
- [<span data-ttu-id="50f30-105">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="50f30-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="50f30-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="50f30-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="50f30-107">Microsoft Defender for Office 365、SharePoint、OneDrive、Microsoft Teamsファイルを誤って共有する組織を保護します。</span><span class="sxs-lookup"><span data-stu-id="50f30-107">Microsoft Defender for Office 365 for SharePoint, OneDrive, and Microsoft Teams protects your organization from inadvertently sharing malicious files.</span></span> <span data-ttu-id="50f30-108">詳細については、「[SharePoint、OneDrive、Microsoft Teams の安全な添付ファイル](mdo-for-spo-odb-and-teams.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="50f30-108">For more information, see [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="50f30-109">この記事では、添付ファイルの有効化と構成セーフ、SharePoint、OneDrive、およびMicrosoft Teams。</span><span class="sxs-lookup"><span data-stu-id="50f30-109">This article contains the steps for enabling and configuring Safe Attachments for SharePoint, OneDrive, and Microsoft Teams.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="50f30-110">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="50f30-110">What do you need to know before you begin?</span></span>

- <span data-ttu-id="50f30-111"><https://security.microsoft.com> で Microsoft 365 Defender ポータルを開きます。</span><span class="sxs-lookup"><span data-stu-id="50f30-111">You open the Microsoft 365 Defender portal at <https://security.microsoft.com>.</span></span> <span data-ttu-id="50f30-112">[添付ファイル] ページに直接 **移動セーフ開** きます <https://security.microsoft.com/safeattachmentv2> 。</span><span class="sxs-lookup"><span data-stu-id="50f30-112">To go directly to the **Safe Attachments** page, open <https://security.microsoft.com/safeattachmentv2>.</span></span>

- <span data-ttu-id="50f30-113">SharePoint、OneDrive、Microsoft Teams の セーフ 添付ファイルを有効にするには、Microsoft 365 Defender ポータルの組織の管理またはセキュリティ管理者の役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="50f30-113">To turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams, you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Microsoft 365 Defender portal.</span></span> <span data-ttu-id="50f30-114">詳細については、「Defender ポータル[のアクセス許可」をMicrosoft 365してください](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="50f30-114">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="50f30-115">SharePoint Online PowerShell を使用して悪意のあるファイルをダウンロードするユーザーを防ぐには、Azure [](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) AD のグローバル管理者または[SharePoint 管理者](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#sharepoint-administrator)の役割のメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="50f30-115">To use SharePoint Online PowerShell to prevent people from downloading malicious files, you need to be member of the [Global Administrator](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) or [SharePoint Administrator](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#sharepoint-administrator) roles in Azure AD.</span></span>

- <span data-ttu-id="50f30-116">組織で監査ログが有効になっているか確認します。</span><span class="sxs-lookup"><span data-stu-id="50f30-116">Verify that audit logging is enabled for your organization.</span></span> <span data-ttu-id="50f30-117">詳細については、「[監査ログの検索を有効または無効にする](../../compliance/turn-audit-log-search-on-or-off.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="50f30-117">For more information, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

- <span data-ttu-id="50f30-118">設定を有効にするには、最大 30 分かかります。</span><span class="sxs-lookup"><span data-stu-id="50f30-118">Allow up to 30 minutes for the settings to take effect.</span></span>

## <a name="step-1-use-the-microsoft-365-defender-portal-to-turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="50f30-119">手順 1: Microsoft 365 Defender ポータルを使用して、セーフ、SharePoint、OneDriveのMicrosoft Teams</span><span class="sxs-lookup"><span data-stu-id="50f30-119">Step 1: Use the Microsoft 365 Defender portal to turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>

1. <span data-ttu-id="50f30-120">[Defender ポータルMicrosoft 365で、[ポリシー] &[脅威ポリシー] セーフに移動し、[グローバル設定] を \>  \> **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="50f30-120">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat policies** \> **Safe attachments**, and click **Global settings**.</span></span>

2. <span data-ttu-id="50f30-121">表示される **[グローバル設定**] の [Defender を有効にする] Office 365、SharePoint、OneDrive、および **Microsoft Teamsします。**</span><span class="sxs-lookup"><span data-stu-id="50f30-121">In the **Global settings** fly out that appears, go to the **Turn on Defender for Office 365 for SharePoint, OneDrive, and Microsoft Teams** setting.</span></span> <span data-ttu-id="50f30-122">トグルを右に移動し、[トグル] をオンに ![ ](../../media/scc-toggle-on.png) し、セーフ、SharePoint、OneDrive、Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="50f30-122">Move the toggle to the right ![Toggle on](../../media/scc-toggle-on.png) to turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams.</span></span>

   <span data-ttu-id="50f30-123">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="50f30-123">When you're finished, click **Save**.</span></span>

### <a name="use-exchange-online-powershell-to-turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="50f30-124">PowerShell Exchange Onlineを使用して、セーフ、SharePoint、OneDriveの添付ファイルMicrosoft Teams</span><span class="sxs-lookup"><span data-stu-id="50f30-124">Use Exchange Online PowerShell to turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>

<span data-ttu-id="50f30-125">SharePoint、OneDrive、および Microsoft Teams の セーフ 添付ファイルを有効にする場合は[、Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)に接続し、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="50f30-125">If you'd rather use PowerShell to turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) and run the following command:</span></span>

```powershell
Set-AtpPolicyForO365 -EnableATPForSPOTeamsODB $true
```

<span data-ttu-id="50f30-126">構文とパラメーターの詳細については [、「Set-AtpPolicyForO365」を参照してください](/powershell/module/exchange/set-atppolicyforo365)。</span><span class="sxs-lookup"><span data-stu-id="50f30-126">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365).</span></span>

## <a name="step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files"></a><span data-ttu-id="50f30-127">手順 2: (推奨) オンライン PowerShell SharePointを使用して、ユーザーが悪意のあるファイルをダウンロードすることを防止する</span><span class="sxs-lookup"><span data-stu-id="50f30-127">Step 2: (Recommended) Use SharePoint Online PowerShell to prevent users from downloading malicious files</span></span>

<span data-ttu-id="50f30-128">既定では、ユーザーは ATP によって検出された悪意のあるファイルを開く、移動、コピー、または共有できます。</span><span class="sxs-lookup"><span data-stu-id="50f30-128">By default, users can't open, move, copy, or share malicious files that are detected by ATP.</span></span> <span data-ttu-id="50f30-129">ただし、悪意のあるファイルを削除してダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="50f30-129">However, they can delete and download malicious files.</span></span>

<span data-ttu-id="50f30-130">ユーザーが悪意のあるファイルをダウンロードできない場合は、オンライン[powerShell SharePointに](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)接続し、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="50f30-130">To prevent users from downloading malicious files, [connect to SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) and run the following command:</span></span>

```powershell
Set-SPOTenant -DisallowInfectedFileDownload $true
```

<span data-ttu-id="50f30-131">**注**:</span><span class="sxs-lookup"><span data-stu-id="50f30-131">**Notes**:</span></span>

- <span data-ttu-id="50f30-132">この設定は、ユーザーと管理者の両方に影響します。</span><span class="sxs-lookup"><span data-stu-id="50f30-132">This setting affects both users and admins.</span></span>
- <span data-ttu-id="50f30-133">ユーザーは引き続き悪意のあるファイルを削除できます。</span><span class="sxs-lookup"><span data-stu-id="50f30-133">People can still delete malicious files.</span></span>

<span data-ttu-id="50f30-134">構文とパラメーターの詳細については [、「Set-SPOTenant」を参照してください](/powershell/module/sharepoint-online/Set-SPOTenant)。</span><span class="sxs-lookup"><span data-stu-id="50f30-134">For detailed syntax and parameter information, see [Set-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant).</span></span>

## <a name="step-3-recommended-use-the-microsoft-365-defender-portal-to-create-an-alert-policy-for-detected-files"></a><span data-ttu-id="50f30-135">手順 3 (推奨) 検出されたファイルMicrosoft 365ポリシーを作成するには、Defender ポータルの管理者ポータルを使用します。</span><span class="sxs-lookup"><span data-stu-id="50f30-135">Step 3 (Recommended) Use the Microsoft 365 Defender portal to create an alert policy for detected files</span></span>

<span data-ttu-id="50f30-136">SharePoint、OneDrive、および Microsoft Teams の添付ファイルが悪意のあるファイルを検出したときに、セーフ 管理者に通知するアラート ポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="50f30-136">You can create an alert policy that notifies you and other admins when Safe Attachments for SharePoint, OneDrive, and Microsoft Teams detects a malicious file.</span></span> <span data-ttu-id="50f30-137">アラートの詳細については、「Defender ポータルでアクティビティ通知を作成[する」をMicrosoft 365してください](../../compliance/create-activity-alerts.md)。</span><span class="sxs-lookup"><span data-stu-id="50f30-137">To learn more about alerts, see [Create activity alerts in the Microsoft 365 Defender portal](../../compliance/create-activity-alerts.md).</span></span>

1. <span data-ttu-id="50f30-138">Defender ポータル [Microsoft 365に](https://security.microsoft.com)移動し、[ポリシー] &**アラート** \> **ポリシーを** 開きます <https://security.microsoft.com/alertpolicies> 。</span><span class="sxs-lookup"><span data-stu-id="50f30-138">In the [Microsoft 365 Defender portal](https://security.microsoft.com), go to **Policies & rules** \> **Alert policy** or open <https://security.microsoft.com/alertpolicies>.</span></span>

2. <span data-ttu-id="50f30-139">[アラート ポリシー **] ページで** 、[新しいアラート ポリシー **] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="50f30-139">On the **Alert policy** page, click **New alert policy**.</span></span>

3. <span data-ttu-id="50f30-140">新 **しいアラート ポリシー ウィザード** がフライアウトで開きます。[アラートに **名前を付け] ページ** で、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="50f30-140">The **New alert policy** wizard opens in a fly out. On the **Name your alert** page, configure the following settings:</span></span>

   - <span data-ttu-id="50f30-141">**名前**: 一意でわかりやすい名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="50f30-141">**Name**: Type a unique and descriptive name.</span></span> <span data-ttu-id="50f30-142">たとえば、ライブラリ内の悪意のあるファイル。</span><span class="sxs-lookup"><span data-stu-id="50f30-142">For example, Malicious Files in Libraries.</span></span>
   - <span data-ttu-id="50f30-143">**説明**: オプションの説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="50f30-143">**Description**: Type an optional description.</span></span> <span data-ttu-id="50f30-144">たとえば、悪意のあるファイルがオンライン、SharePoint、またはOneDriveで検出Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="50f30-144">For example, Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams.</span></span>
   - <span data-ttu-id="50f30-145">**重大度 :** 既定値 [低]**を選択** のままにするか、[中] または [高]**を\*\*\*\*選択します**。</span><span class="sxs-lookup"><span data-stu-id="50f30-145">**Severity**: Leave the default value **Low** selected, or select **Medium** or **High**.</span></span>
   - <span data-ttu-id="50f30-146">**カテゴリ**: [脅威の **管理] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="50f30-146">**Category**: Select **Threat management**.</span></span>

   <span data-ttu-id="50f30-147">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="50f30-147">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="50f30-148">[アラート設定 **の作成] ページ** で、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="50f30-148">On the **Create alert settings** page, configure the following settings:</span></span>

   - <span data-ttu-id="50f30-149">**何を通知しますか?:** アクティビティは: ファイル内の **検出されたマルウェアを選択します**。</span><span class="sxs-lookup"><span data-stu-id="50f30-149">**What do you want to alert on?: Activity is**: Select **Detected malware in file**.</span></span>
   - <span data-ttu-id="50f30-150">**アラートをトリガーする方法:** アクティビティが選択したルールと一致する度に既定値 **のままに** します。</span><span class="sxs-lookup"><span data-stu-id="50f30-150">**How do you want the alert to be triggered?**: Leave the default value **Every time an activity matches the rule** selected.</span></span>

   <span data-ttu-id="50f30-151">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="50f30-151">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="50f30-152">[受信者 **の設定] ページで** 、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="50f30-152">On the **Set your recipients** page, configure the following settings:</span></span>

   - <span data-ttu-id="50f30-153">**電子メール通知の送信**: この設定が選択されているのを確認します。</span><span class="sxs-lookup"><span data-stu-id="50f30-153">**Send email notifications**: Verify this setting is selected.</span></span> <span data-ttu-id="50f30-154">[ **電子メールの受信者]** ボックスで、悪意のあるファイルが検出された場合に通知を受け取る必要がある 1 つ以上のグローバル管理者、セキュリティ管理者、またはセキュリティ リーダーを選択します。</span><span class="sxs-lookup"><span data-stu-id="50f30-154">In the **Email recipients** box, select one or more global administrators, security administrators, or security readers who should receive notification when a malicious file is detected.</span></span>
   - <span data-ttu-id="50f30-155">**1 日の通知** の制限 : 既定値 [制限 **なし] を** 選択のままにします。</span><span class="sxs-lookup"><span data-stu-id="50f30-155">**Daily notification limit**: Leave the default value **No limit** selected.</span></span>

   <span data-ttu-id="50f30-156">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="50f30-156">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="50f30-157">[設定 **の確認] ページで** 設定を確認し、任意のセクションで [編集] をクリックして変更を加えます。</span><span class="sxs-lookup"><span data-stu-id="50f30-157">On the **Review your settings** page, review the settings, and click **Edit** in any of the sections to make changes.</span></span>

   <span data-ttu-id="50f30-158">[ポリシー **をすぐ有効** にしますか? ] セクションで、既定値 **は [は** い] のままにし、右クリックしてオンにしてください。</span><span class="sxs-lookup"><span data-stu-id="50f30-158">In the **Do you want to turn the policy on right away?** section, leave the default value **Yes, turn it on right away** selected.</span></span>

   <span data-ttu-id="50f30-159">完了したら、 **[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="50f30-159">When you're finished, click **Finish**.</span></span>

### <a name="use-security--compliance-powershell-to-create-an-alert-policy-for-detected-files"></a><span data-ttu-id="50f30-160">セキュリティ ポリシー&コンプライアンス PowerShell を使用して、検出されたファイルのアラート ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="50f30-160">Use Security & Compliance PowerShell to create an alert policy for detected files</span></span>

<span data-ttu-id="50f30-161">前のセクションで説明したように、PowerShell を使用して同じアラート ポリシーを作成する場合は、セキュリティ & コンプライアンス センター [PowerShell](/powershell/exchange/connect-to-scc-powershell) に接続し、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="50f30-161">If you'd rather use PowerShell to create the same alert policy as described in the previous section, [connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) and run the following command:</span></span>

```powershell
New-ActivityAlert -Name "Malicious Files in Libraries" -Description "Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams" -Category ThreatManagement -Operation FileMalwareDetected -NotifyUser "admin1@contoso.com","admin2@contoso.com"
```

<span data-ttu-id="50f30-162">**注**: 既定の _重大度の値は_ 低です。</span><span class="sxs-lookup"><span data-stu-id="50f30-162">**Note**: The default _Severity_ value is Low.</span></span> <span data-ttu-id="50f30-163">中または高を指定するには、コマンドに _Severity_ パラメーターと値を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="50f30-163">To specify Medium or High, include the _Severity_ parameter and value in the command.</span></span>

<span data-ttu-id="50f30-164">構文とパラメーターの詳細については [、「New-ActivityAlert」を参照してください](/powershell/module/exchange/new-activityalert)。</span><span class="sxs-lookup"><span data-stu-id="50f30-164">For detailed syntax and parameter information, see [New-ActivityAlert](/powershell/module/exchange/new-activityalert).</span></span>

### <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="50f30-165">正常な動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="50f30-165">How do you know these procedures worked?</span></span>

- <span data-ttu-id="50f30-166">SharePoint、OneDrive、および Microsoft Teams の セーフ 添付ファイルが正常に有効になっていることを確認するには、次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="50f30-166">To verify that you've successfully turned on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams, use either of the following steps:</span></span>

  - <span data-ttu-id="50f30-167">Microsoft 365 [Defender](https://security.microsoft.com)ポータルで、[ポリシー & **rules** Threat \> **Policies** \> **セーフ** 添付ファイル] に移動し、[グローバル設定] を選択し、[SharePoint、OneDrive、および Microsoft Teams の Office 365 の Defender を有効にする] 設定の値を **確認** します。</span><span class="sxs-lookup"><span data-stu-id="50f30-167">In the [Microsoft 365 Defender portal](https://security.microsoft.com), go to **Policies & rules** \> **Threat Policies** \> **Safe attachments**, select **Global settings**, and verify the value of the **Turn on Defender for Office 365 for SharePoint, OneDrive, and Microsoft Teams** setting.</span></span>

  - <span data-ttu-id="50f30-168">PowerShell Exchange Onlineで、次のコマンドを実行してプロパティ設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="50f30-168">In Exchange Online PowerShell, run the following command to verify the property setting:</span></span>

    ```powershell
    Get-AtpPolicyForO365 | Format-List EnableATPForSPOTeamsODB
    ```

    <span data-ttu-id="50f30-169">構文とパラメーターの詳細については [、「Get-AtpPolicyForO365」を参照してください](/powershell/module/exchange/get-atppolicyforo365)。</span><span class="sxs-lookup"><span data-stu-id="50f30-169">For detailed syntax and parameter information, see [Get-AtpPolicyForO365](/powershell/module/exchange/get-atppolicyforo365).</span></span>

- <span data-ttu-id="50f30-170">悪意のあるファイルのダウンロードが正常にブロックされたことを確認するには、SharePoint Online PowerShell を開き、次のコマンドを実行してプロパティ値を確認します。</span><span class="sxs-lookup"><span data-stu-id="50f30-170">To verify that you've successfully blocked people from downloading malicious files, open SharePoint Online PowerShell, and run the following command to verify the property value:</span></span>

  ```powershell
  Get-SPOTenant | Format-List DisallowInfectedFileDownload
  ```

  <span data-ttu-id="50f30-171">構文とパラメーターの詳細については [、「Get-SPOTenant」を参照してください](/powershell/module/sharepoint-online/Set-SPOTenant)。</span><span class="sxs-lookup"><span data-stu-id="50f30-171">For detailed syntax and parameter information, see [Get-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant).</span></span>

- <span data-ttu-id="50f30-172">検出されたファイルのアラート ポリシーが正常に構成されたことを確認するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="50f30-172">To verify that you've successfully configured an alert policy for detected files, use any of the following steps:</span></span>

  - <span data-ttu-id="50f30-173">Defender ポータルMicrosoft 365に移動し、[ポリシー]  &アラート ポリシーを選択し、 \>  \> 設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="50f30-173">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Alert policy** \> select the alert policy, and verify the settings.</span></span>

  - <span data-ttu-id="50f30-174">Defender Microsoft 365 PowerShell で、アラート ポリシーの名前に置き換え、次のコマンドを実行し、プロパティ \<AlertPolicyName\> 値を確認します。</span><span class="sxs-lookup"><span data-stu-id="50f30-174">In Microsoft 365 Defender portal PowerShell, replace \<AlertPolicyName\> with the name of the alert policy, run the following command, and verify the property values:</span></span>

    ```powershell
    Get-ActivityAlert -Identity "<AlertPolicyName>"
    ```

    <span data-ttu-id="50f30-175">構文とパラメーターの詳細については [、「Get-ActivityAlert」を参照してください](/powershell/module/exchange/get-activityalert)。</span><span class="sxs-lookup"><span data-stu-id="50f30-175">For detailed syntax and parameter information, see [Get-ActivityAlert](/powershell/module/exchange/get-activityalert).</span></span>

- <span data-ttu-id="50f30-176">脅威保護[の状態レポートを使用](view-email-security-reports.md#threat-protection-status-report)して、検出されたファイルに関する情報を、SharePoint、OneDrive、およびMicrosoft Teams。</span><span class="sxs-lookup"><span data-stu-id="50f30-176">Use the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report) to view information about detected files in SharePoint, OneDrive, and Microsoft Teams.</span></span> <span data-ttu-id="50f30-177">具体的には、[データの表示方法: コンテンツ マルウェア **] ビュー \> を使用** できます。</span><span class="sxs-lookup"><span data-stu-id="50f30-177">Specifically, you can use the **View data by: Content \> Malware** view.</span></span>