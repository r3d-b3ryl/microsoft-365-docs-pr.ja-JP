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
description: 管理者は、検出されたファイルのアラートを設定する方法など、SharePoint、OneDrive、Microsoft Teams の安全な添付ファイルを有効にする方法について説明します。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9688af82d194b1818d6bd3323d39bde51db20cb2
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286371"
---
# <a name="turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="1f0a5-103">SharePoint、OneDrive、Microsoft Teams 用の ATP を有効にする</span><span class="sxs-lookup"><span data-stu-id="1f0a5-103">Turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="1f0a5-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="1f0a5-104">**Applies to**</span></span>
- [<span data-ttu-id="1f0a5-105">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="1f0a5-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="1f0a5-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1f0a5-106">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="1f0a5-107">Microsoft Defender for Office 365 for SharePoint、OneDrive、および Microsoft Teams は、悪意のあるファイルを誤って共有する組織を保護します。</span><span class="sxs-lookup"><span data-stu-id="1f0a5-107">Microsoft Defender for Office 365 for SharePoint, OneDrive, and Microsoft Teams protects your organization from inadvertently sharing malicious files.</span></span> <span data-ttu-id="1f0a5-108">詳細については [、「SharePoint、OneDrive、Microsoft Teams の安全な添付ファイル」を参照してください](atp-for-spo-odb-and-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="1f0a5-108">For more information, see [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="1f0a5-109">この記事では、SharePoint、OneDrive、Microsoft Teams の安全な添付ファイルを有効にし、構成する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="1f0a5-109">This article contains the steps for enabling and configuring Safe Attachments for SharePoint, OneDrive, and Microsoft Teams.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="1f0a5-110">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="1f0a5-110">What do you need to know before you begin?</span></span>

- <span data-ttu-id="1f0a5-111"><https://protection.office.com> でセキュリティ/コンプライアンス センターを開きます。</span><span class="sxs-lookup"><span data-stu-id="1f0a5-111">You open the Security & Compliance Center at <https://protection.office.com>.</span></span> <span data-ttu-id="1f0a5-112">[ATP の安全な添付ファイル **] ページに直接移動するには** 、開きます <https://protection.office.com/safeattachmentv2> 。</span><span class="sxs-lookup"><span data-stu-id="1f0a5-112">To go directly to the **ATP Safe Attachments** page, open <https://protection.office.com/safeattachmentv2>.</span></span>

- <span data-ttu-id="1f0a5-113">SharePoint、OneDrive、および Microsoft Teams の安全な添付ファイルを有効にする場合は、セキュリティ/コンプライアンスセンターの組織の管理役割グループまたはセキュリティ管理者役割グループのメンバーである必要&があります。</span><span class="sxs-lookup"><span data-stu-id="1f0a5-113">To turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams, you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="1f0a5-114">詳細については、「[セキュリティ/コンプライアンス センターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1f0a5-114">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="1f0a5-115">SharePoint Online PowerShell を使用してユーザーが悪意のあるファイルをダウンロードするのを防[](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator)ぐには、Azure AD のグローバル管理者または[SharePoint](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#sharepoint-administrator)管理者ロールのメンバーである必要AD。</span><span class="sxs-lookup"><span data-stu-id="1f0a5-115">To use SharePoint Online PowerShell to prevent people from downloading malicious files, you need to be member of the [Global Administrator](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) or [SharePoint Administrator](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#sharepoint-administrator) roles in Azure AD.</span></span>

- <span data-ttu-id="1f0a5-116">組織で監査ログが有効になっているか確認します。</span><span class="sxs-lookup"><span data-stu-id="1f0a5-116">Verify that audit logging is enabled for your organization.</span></span> <span data-ttu-id="1f0a5-117">詳細については、「[監査ログの検索を有効または無効にする](../../compliance/turn-audit-log-search-on-or-off.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1f0a5-117">For more information, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

- <span data-ttu-id="1f0a5-118">設定を有効にできる時間は最大 30 分です。</span><span class="sxs-lookup"><span data-stu-id="1f0a5-118">Allow up to 30 minutes for the settings to take effect.</span></span>

## <a name="step-1-use-the-security--compliance-center-to-turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="1f0a5-119">手順 1: セキュリティ/コンプライアンス センター&使用して、SharePoint、OneDrive、Microsoft Teams の安全な添付ファイルを有効にする</span><span class="sxs-lookup"><span data-stu-id="1f0a5-119">Step 1: Use the Security & Compliance Center to turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>

1. <span data-ttu-id="1f0a5-120">セキュリティ/コンプライアンス センター&、**脅威管理** ポリシー ATP の安全な添付ファイルに移動し、[グローバル設定] \>  \> を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="1f0a5-120">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**, and click **Global settings**.</span></span>

2. <span data-ttu-id="1f0a5-121">表示される **グローバル設定** のフライアウトで **、SharePoint、OneDrive、Microsoft Teams の Office 365** に対して Defender を有効にする設定に移動します。</span><span class="sxs-lookup"><span data-stu-id="1f0a5-121">In the **Global settings** fly out that appears, go to the **Turn on Defender for Office 365 for SharePoint, OneDrive, and Microsoft Teams** setting.</span></span> <span data-ttu-id="1f0a5-122">トグルを右のトグルに移動して ![ ](../../media/scc-toggle-on.png) 、SharePoint、OneDrive、Microsoft Teams の安全な添付ファイルを有効にします。</span><span class="sxs-lookup"><span data-stu-id="1f0a5-122">Move the toggle to the right ![Toggle on](../../media/scc-toggle-on.png) to turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams.</span></span>

   <span data-ttu-id="1f0a5-123">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1f0a5-123">When you're finished, click **Save**.</span></span>

### <a name="use-exchange-online-powershell-to-turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="1f0a5-124">Exchange Online PowerShell を使用して SharePoint、OneDrive、Microsoft Teams の安全な添付ファイルを有効にする</span><span class="sxs-lookup"><span data-stu-id="1f0a5-124">Use Exchange Online PowerShell to turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>

<span data-ttu-id="1f0a5-125">PowerShell を使用して SharePoint、OneDrive、Microsoft Teams の安全な添付ファイルを有効にする場合は [、Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) に接続し、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="1f0a5-125">If you'd rather use PowerShell to turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams, [connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) and run the following command:</span></span>

```powershell
Set-AtpPolicyForO365 -EnableATPForSPOTeamsODB $true
```

<span data-ttu-id="1f0a5-126">構文およびパラメーターの詳細については [、「Set-AtpPolicyForO365」を参照](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365)してください。</span><span class="sxs-lookup"><span data-stu-id="1f0a5-126">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).</span></span>

## <a name="step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files"></a><span data-ttu-id="1f0a5-127">手順 2: (推奨) SharePoint Online PowerShell を使用して、ユーザーが悪意のあるファイルをダウンロードすることを防ぐ</span><span class="sxs-lookup"><span data-stu-id="1f0a5-127">Step 2: (Recommended) Use SharePoint Online PowerShell to prevent users from downloading malicious files</span></span>

<span data-ttu-id="1f0a5-128">既定では、ユーザーは ATP によって検出された悪意のあるファイルを開く、移動する、コピーする、共有できない。</span><span class="sxs-lookup"><span data-stu-id="1f0a5-128">By default, users can't open, move, copy, or share malicious files that are detected by ATP.</span></span> <span data-ttu-id="1f0a5-129">ただし、悪意のあるファイルを削除してダウンロードすることができます。</span><span class="sxs-lookup"><span data-stu-id="1f0a5-129">However, they can delete and download malicious files.</span></span>

<span data-ttu-id="1f0a5-130">ユーザーが悪意のあるファイルをダウンロードできないのを防ぐには [、SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) に接続し、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="1f0a5-130">To prevent users from downloading malicious files, [connect to SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) and run the following command:</span></span>

```powershell
Set-SPOTenant -DisallowInfectedFileDownload $true
```

<span data-ttu-id="1f0a5-131">**注**:</span><span class="sxs-lookup"><span data-stu-id="1f0a5-131">**Notes**:</span></span>

- <span data-ttu-id="1f0a5-132">この設定は、ユーザーと管理者の両方に影響します。</span><span class="sxs-lookup"><span data-stu-id="1f0a5-132">This setting affects both users and admins.</span></span>
- <span data-ttu-id="1f0a5-133">悪意のあるファイルは引き続き削除できます。</span><span class="sxs-lookup"><span data-stu-id="1f0a5-133">People can still delete malicious files.</span></span>

<span data-ttu-id="1f0a5-134">構文およびパラメーターの詳細については [、「Set-SPOTenant」を参照してください](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)。</span><span class="sxs-lookup"><span data-stu-id="1f0a5-134">For detailed syntax and parameter information, see [Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant).</span></span>

## <a name="step-3-recommended-use-the-security--compliance-center-to-create-an-alert-policy-for-detected-files"></a><span data-ttu-id="1f0a5-135">手順 3 (推奨) セキュリティ センターとコンプライアンス センター&使用して、検出されたファイルのアラート ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="1f0a5-135">Step 3 (Recommended) Use the Security & Compliance Center to create an alert policy for detected files</span></span>

<span data-ttu-id="1f0a5-136">SharePoint、OneDrive、および Microsoft Teams の安全な添付ファイルが悪意のあるファイルを検出したときに、自分や他の管理者に通知するアラート ポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="1f0a5-136">You can create an alert policy that notifies you and other admins when Safe Attachments for SharePoint, OneDrive, and Microsoft Teams detects a malicious file.</span></span> <span data-ttu-id="1f0a5-137">アラートの詳細については、「セキュリティ/コンプライアンス センターでのアクティビティアラート& [参照してください](../../compliance/create-activity-alerts.md)。</span><span class="sxs-lookup"><span data-stu-id="1f0a5-137">To learn more about alerts, see [Create activity alerts in the Security & Compliance Center](../../compliance/create-activity-alerts.md).</span></span>

1. <span data-ttu-id="1f0a5-138">セキュリティ/ [コンプライアンス センターで&](https://protection.office.com)アラート **ポリシー** に移動するか \> **、開** きます <https://protection.office.com/alertpolicies> 。</span><span class="sxs-lookup"><span data-stu-id="1f0a5-138">In the [Security & Compliance Center](https://protection.office.com), go to **Alerts** \> **Alert policies** or open <https://protection.office.com/alertpolicies>.</span></span>

2. <span data-ttu-id="1f0a5-139">[アラート **ポリシー] ページで、[** 新しいアラート **ポリシー] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="1f0a5-139">On the **Alert policies** page, click **New alert policy**.</span></span>

3. <span data-ttu-id="1f0a5-140">アラート **ポリシーの新規ウィザード** がフライアウトで開きます。[アラート **に名前を付け] ページで** 、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="1f0a5-140">The **New alert policy** wizard opens in a fly out. On the **Name your alert** page, configure the following settings:</span></span>

   - <span data-ttu-id="1f0a5-141">**名前**: 一意でわかりやすい名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="1f0a5-141">**Name**: Type a unique and descriptive name.</span></span> <span data-ttu-id="1f0a5-142">たとえば、ライブラリ内の悪意のあるファイル。</span><span class="sxs-lookup"><span data-stu-id="1f0a5-142">For example, Malicious Files in Libraries.</span></span>
   - <span data-ttu-id="1f0a5-143">**説明**: オプションの説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="1f0a5-143">**Description**: Type an optional description.</span></span> <span data-ttu-id="1f0a5-144">たとえば、SharePoint Online、OneDrive、または Microsoft Teams で悪意のあるファイルが検出された場合に管理者に通知します。</span><span class="sxs-lookup"><span data-stu-id="1f0a5-144">For example, Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams.</span></span>
   - <span data-ttu-id="1f0a5-145">**重要度 :** 既定値の [低] **を選択** のままにするか、[中] または [高 **]** を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="1f0a5-145">**Severity**: Leave the default value **Low** selected, or select **Medium** or **High**.</span></span>
   - <span data-ttu-id="1f0a5-146">**Select a category**: Select **Threat management**.</span><span class="sxs-lookup"><span data-stu-id="1f0a5-146">**Select a category**: Select **Threat management**.</span></span>

   <span data-ttu-id="1f0a5-147">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1f0a5-147">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="1f0a5-148">[アラート **設定の作成] ページ** で、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="1f0a5-148">On the **Create alert settings** page, configure the following settings:</span></span>

   - <span data-ttu-id="1f0a5-149">**What do you want to alert on?: Activity is:** Select **Detected malware in file**.</span><span class="sxs-lookup"><span data-stu-id="1f0a5-149">**What do you want to alert on?: Activity is**: Select **Detected malware in file**.</span></span>
   - <span data-ttu-id="1f0a5-150">**アラートをトリガー** する方法: アクティビティが選択したルールと一致する度に既定値 **のままに** します。</span><span class="sxs-lookup"><span data-stu-id="1f0a5-150">**How do you want the alert to be triggered?**: Leave the default value **Every time an activity matches the rule** selected.</span></span>

   <span data-ttu-id="1f0a5-151">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1f0a5-151">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="1f0a5-152">[受信者 **の設定] ページで** 、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="1f0a5-152">On the **Set your recipients** page, configure the following settings:</span></span>

   - <span data-ttu-id="1f0a5-153">**電子メール通知の送信**: この設定が選択されているのを確認します。</span><span class="sxs-lookup"><span data-stu-id="1f0a5-153">**Send email notifications**: Verify this setting is selected.</span></span> <span data-ttu-id="1f0a5-154">[ **電子メールの受信者** ] ボックスで、悪意のあるファイルが検出された場合に通知を受け取る必要がある 1 人または複数のグローバル管理者、セキュリティ管理者、またはセキュリティ 閲覧者を選択します。</span><span class="sxs-lookup"><span data-stu-id="1f0a5-154">In the **Email recipients** box, select one or more global administrators, security administrators, or security readers who should receive notification when a malicious file is detected.</span></span>
   - <span data-ttu-id="1f0a5-155">**1 日の通知** 制限 : 既定値 [制限 **なし] を** 選択したままにしてください。</span><span class="sxs-lookup"><span data-stu-id="1f0a5-155">**Daily notification limit**: Leave the default value **No limit** selected.</span></span>

   <span data-ttu-id="1f0a5-156">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1f0a5-156">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="1f0a5-157">[設定 **の確認] ページ** で設定を確認し、セクションの [編集] をクリックして変更を行います。</span><span class="sxs-lookup"><span data-stu-id="1f0a5-157">On the **Review your settings** page, review the settings, and click **Edit** in any of the sections to make changes.</span></span>

   <span data-ttu-id="1f0a5-158">[ **ポリシーを今すぐ** 有効にしますか? ] セクションで、既定値 **は [は** い] のままにし、そのままオンにしてください。</span><span class="sxs-lookup"><span data-stu-id="1f0a5-158">In the **Do you want to turn the policy on right away?** section, leave the default value **Yes, turn it on right away** selected.</span></span>

   <span data-ttu-id="1f0a5-159">完了したら、 **[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1f0a5-159">When you're finished, click **Finish**.</span></span>

### <a name="use-security--compliance-powershell-to-create-an-alert-policy-for-detected-files"></a><span data-ttu-id="1f0a5-160">Security & Compliance PowerShell を使用して、検出されたファイルのアラート ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="1f0a5-160">Use Security & Compliance PowerShell to create an alert policy for detected files</span></span>

<span data-ttu-id="1f0a5-161">前のセクションで説明したのと同じアラート ポリシーを PowerShell を使用して作成する場合は、セキュリティ & コンプライアンス センター [の PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) に接続し、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="1f0a5-161">If you'd rather use PowerShell to create the same alert policy as described in the previous section, [connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) and run the following command:</span></span>

```powershell
New-ActivityAlert -Name "Malicious Files in Libraries" -Description "Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams" -Category ThreatManagement -Operation FileMalwareDetected -NotifyUser "admin1@contoso.com","admin2@contoso.com"
```

<span data-ttu-id="1f0a5-162">**注**: 既定の _重要度の値_ は低です。</span><span class="sxs-lookup"><span data-stu-id="1f0a5-162">**Note**: The default _Severity_ value is Low.</span></span> <span data-ttu-id="1f0a5-163">中または高を指定するには、コマンドに _Severity_ パラメーターと値を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="1f0a5-163">To specify Medium or High, include the _Severity_ parameter and value in the command.</span></span>

<span data-ttu-id="1f0a5-164">構文およびパラメーターの詳細については [、「New-ActivityAlert」を参照してください](https://docs.microsoft.com/powershell/module/exchange/new-activityalert)。</span><span class="sxs-lookup"><span data-stu-id="1f0a5-164">For detailed syntax and parameter information, see [New-ActivityAlert](https://docs.microsoft.com/powershell/module/exchange/new-activityalert).</span></span>

### <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="1f0a5-165">正常な動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="1f0a5-165">How do you know these procedures worked?</span></span>

- <span data-ttu-id="1f0a5-166">SharePoint、OneDrive、Microsoft Teams の安全な添付ファイルが正常に有効になっていることを確認するには、次のいずれかの手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="1f0a5-166">To verify that you've successfully turned on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams, use either of the following steps:</span></span>

  - <span data-ttu-id="1f0a5-167">セキュリティ [](https://protection.office.com)& コンプライアンス センターで、脅威管理ポリシー  ATP の安全な添付ファイルに移動し、グローバル設定を選択して \>  \> **、SharePoint、OneDrive、Microsoft Teams の Office 365** の Defender を有効にする設定の値を確認します。</span><span class="sxs-lookup"><span data-stu-id="1f0a5-167">In the [Security & Compliance Center](https://protection.office.com), go to **Threat management** \> **Policy** \> **ATP Safe Attachments**, select **Global settings**, and verify the value of the **Turn on Defender for Office 365 for SharePoint, OneDrive, and Microsoft Teams** setting.</span></span>

  - <span data-ttu-id="1f0a5-168">Exchange Online PowerShell で、次のコマンドを実行してプロパティの設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="1f0a5-168">In Exchange Online PowerShell, run the following command to verify the property setting:</span></span>

    ```powershell
    Get-AtpPolicyForO365 | Format-List EnableATPForSPOTeamsODB
    ```

    <span data-ttu-id="1f0a5-169">構文およびパラメーターの詳細については [、Get-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/get-atppolicyforo365)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1f0a5-169">For detailed syntax and parameter information, see [Get-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/get-atppolicyforo365).</span></span>

- <span data-ttu-id="1f0a5-170">悪意のあるファイルのダウンロードが正常にブロックされたことを確認するには、SharePoint Online PowerShell を開き、次のコマンドを実行してプロパティ値を確認します。</span><span class="sxs-lookup"><span data-stu-id="1f0a5-170">To verify that you've successfully blocked people from downloading malicious files, open SharePoint Online PowerShell, and run the following command to verify the property value:</span></span>

  ```powershell
  Get-SPOTenant | Format-List DisallowInfectedFileDownload
  ```

  <span data-ttu-id="1f0a5-171">構文およびパラメーターの詳細については [、「Get-SPOTenant」を参照してください](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)。</span><span class="sxs-lookup"><span data-stu-id="1f0a5-171">For detailed syntax and parameter information, see [Get-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant).</span></span>

- <span data-ttu-id="1f0a5-172">検出されたファイルに対してアラート ポリシーが正常に構成されたことを確認するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="1f0a5-172">To verify that you've successfully configured an alert policy for detected files, use any of the following steps:</span></span>

  - <span data-ttu-id="1f0a5-173">セキュリティ/コンプライアンス センター&アラート アラート ポリシーに移動し、アラート ポリシーを選択し、 \>  \> 設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="1f0a5-173">In the Security & Compliance Center, go to **Alerts** \> **Alert policies** \> select the alert policy, and verify the settings.</span></span>

  - <span data-ttu-id="1f0a5-174">Security & Compliance Center PowerShell で、アラート ポリシーの名前に置き換え、次のコマンドを実行して、プロパティ値 \<AlertPolicyName\> を確認します。</span><span class="sxs-lookup"><span data-stu-id="1f0a5-174">In Security & Compliance Center PowerShell, replace \<AlertPolicyName\> with the name of the alert policy, run the following command, and verify the property values:</span></span>

    ```powershell
    Get-ActivityAlert -Identity "<AlertPolicyName>"
    ```

    <span data-ttu-id="1f0a5-175">構文およびパラメーターの詳細については [、「Get-ActivityAlert」を参照してください](https://docs.microsoft.com/powershell/module/exchange/get-activityalert)。</span><span class="sxs-lookup"><span data-stu-id="1f0a5-175">For detailed syntax and parameter information, see [Get-ActivityAlert](https://docs.microsoft.com/powershell/module/exchange/get-activityalert).</span></span>

- <span data-ttu-id="1f0a5-176">脅威保護 [状態レポートを使用して](view-email-security-reports.md#threat-protection-status-report) 、SharePoint、OneDrive、および Microsoft Teams で検出されたファイルに関する情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="1f0a5-176">Use the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report) to view information about detected files in SharePoint, OneDrive, and Microsoft Teams.</span></span> <span data-ttu-id="1f0a5-177">具体的には、[データの表示方法: コンテンツ マルウェア] ビュー **\> を使用** できます。</span><span class="sxs-lookup"><span data-stu-id="1f0a5-177">Specifically, you can use the **View data by: Content \> Malware** view.</span></span>
