---
title: 不正同意の付与を検出して修復する
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.collection:
- o365_security_incident_response
- M365-security-compliance
localization_priority: Normal
search.appverid:
- MET150
description: 365 で不正な同意許可攻撃を認識して修復するMicrosoft Officeします。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 4a9b3ff11acb32a4b3038cc18922f8e22fda0b4c
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51061988"
---
# <a name="detect-and-remediate-illicit-consent-grants"></a><span data-ttu-id="80629-103">不正同意の付与を検出して修復する</span><span class="sxs-lookup"><span data-stu-id="80629-103">Detect and Remediate Illicit Consent Grants</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="80629-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="80629-104">**Applies to**</span></span>
- [<span data-ttu-id="80629-105">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="80629-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="80629-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="80629-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="80629-107">**概要**  365 で不正な同意許可攻撃を認識して修復する方法Officeします。</span><span class="sxs-lookup"><span data-stu-id="80629-107">**Summary**  Learn how to recognize and remediate the illicit consent grants attack in Office 365.</span></span>

## <a name="what-is-the-illicit-consent-grant-attack-in-office-365"></a><span data-ttu-id="80629-108">365 の不正な同意付与攻撃Office。</span><span class="sxs-lookup"><span data-stu-id="80629-108">What is the illicit consent grant attack in Office 365?</span></span>

<span data-ttu-id="80629-109">不正な同意許可攻撃では、攻撃者は連絡先情報、電子メール、ドキュメントなどのデータへのアクセスを要求する Azure 登録アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="80629-109">In an illicit consent grant attack, the attacker creates an Azure-registered application that requests access to data such as contact information, email, or documents.</span></span> <span data-ttu-id="80629-110">その後、攻撃者はエンド ユーザーに対して、フィッシング攻撃を通じて、または信頼できる Web サイトに不正なコードを挿入することで、アプリケーションが自分のデータにアクセスする同意を与える方法を悪用します。</span><span class="sxs-lookup"><span data-stu-id="80629-110">The attacker then tricks an end user into granting that application consent to access their data either through a phishing attack, or by injecting illicit code into a trusted website.</span></span> <span data-ttu-id="80629-111">不正なアプリケーションに同意が付与された後、組織のアカウントを必要とせずに、アカウント レベルでデータにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="80629-111">After the illicit application has been granted consent, it has account-level access to data without the need for an organizational account.</span></span> <span data-ttu-id="80629-112">侵害されたアカウントのパスワードのリセットやアカウントでの多要素認証 (MFA) の要求など、通常の修復手順は、サード パーティ製のアプリケーションであり、組織の外部であるため、この種類の攻撃に対して有効ではありません。</span><span class="sxs-lookup"><span data-stu-id="80629-112">Normal remediation steps, like resetting passwords for breached accounts or requiring Multi-Factor Authentication (MFA) on accounts, are not effective against this type of attack, since these are third-party applications and are external to the organization.</span></span>

<span data-ttu-id="80629-113">これらの攻撃は、情報を呼び出しているエンティティが人間ではなく自動化だと推測する対話モデルを利用します。</span><span class="sxs-lookup"><span data-stu-id="80629-113">These attacks leverage an interaction model which presumes the entity that is calling the information is automation and not a human.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="80629-114">アプリからの不正な同意許可に問題が発生している疑いはありますか。</span><span class="sxs-lookup"><span data-stu-id="80629-114">Do you suspect you're experiencing problems with illicit consent-grants from an app, right now?</span></span> <span data-ttu-id="80629-115">Microsoft Cloud App Security (MCAS) には、OAuth アプリを検出、調査、修復するためのツールがあります。</span><span class="sxs-lookup"><span data-stu-id="80629-115">Microsoft Cloud App Security (MCAS) has tools to detect, investigate, and remediate your OAuth apps.</span></span> <span data-ttu-id="80629-116">この MCAS の記事には、リスクの高い [OAuth](/cloud-app-security/investigate-risky-oauth)アプリの調査について説明するチュートリアルがあります。</span><span class="sxs-lookup"><span data-stu-id="80629-116">This MCAS article has a tutorial that outlines how to go about [investigating risky OAuth apps](/cloud-app-security/investigate-risky-oauth).</span></span> <span data-ttu-id="80629-117">[また、OAuth](/cloud-app-security/app-permission-policy)アプリ ポリシーを設定して、これらのアプリを承認しているアプリ要求のアクセス許可を調査し、これらのアクセス許可要求を広く承認または禁止することもできます。</span><span class="sxs-lookup"><span data-stu-id="80629-117">You can also set [OAuth app policies](/cloud-app-security/app-permission-policy) to investigate app-requested permissions, which users are authorizing these apps, and widely approve or ban these permissions requests.</span></span>

## <a name="what-does-an-illicit-consent-grant-attack-look-like-in-office-365"></a><span data-ttu-id="80629-118">365 の不正な同意付与攻撃Office。</span><span class="sxs-lookup"><span data-stu-id="80629-118">What does an illicit consent grant attack look like in Office 365?</span></span>

<span data-ttu-id="80629-119">監査ログを **検索して、** この攻撃の侵害のインジケーター (IOC) とも呼ばれる兆候を見つける必要があります。</span><span class="sxs-lookup"><span data-stu-id="80629-119">You need to search the **audit log** to find signs, also called Indicators of Compromise (IOC) of this attack.</span></span> <span data-ttu-id="80629-120">多くの Azure 登録アプリケーションと大規模なユーザー ベースを持つ組織の場合、ベスト プラクティスは、組織の同意許可を毎週確認する方法です。</span><span class="sxs-lookup"><span data-stu-id="80629-120">For organizations with many Azure-registered applications and a large user base, the best practice is to review your organizations consent grants on a weekly basis.</span></span>

### <a name="steps-for-finding-signs-of-this-attack"></a><span data-ttu-id="80629-121">この攻撃の兆候を見つける手順</span><span class="sxs-lookup"><span data-stu-id="80629-121">Steps for finding signs of this attack</span></span>

1. <span data-ttu-id="80629-122">で **[セキュリティ & コンプライアンス センター] を開** きます <https://protection.office.com> 。</span><span class="sxs-lookup"><span data-stu-id="80629-122">Open the **Security & Compliance Center** at <https://protection.office.com>.</span></span>

2. <span data-ttu-id="80629-123">[検索] **に移動し** 、[監査 **ログ検索] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="80629-123">Navigate to **Search** and select **Audit log search**.</span></span>

3. <span data-ttu-id="80629-124">検索 (すべてのアクティビティとすべてのユーザー) を選択し、必要に応じて開始日と終了日を入力し、[検索] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="80629-124">Search (all activities and all users) and enter the start date and end date if required and then click **Search**.</span></span>

4. <span data-ttu-id="80629-125">[結果 **のフィルター] を** クリックし、[アクティビティ] フィールドに「アプリケーションへの同意」 **と入力** します。</span><span class="sxs-lookup"><span data-stu-id="80629-125">Click **Filter results** and enter Consent to application in the **Activity** field.</span></span>

5. <span data-ttu-id="80629-126">結果をクリックすると、アクティビティの詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="80629-126">Click on the result to see the details of the activity.</span></span> <span data-ttu-id="80629-127">[詳細情報 **] を** クリックして、アクティビティの詳細を取得します。</span><span class="sxs-lookup"><span data-stu-id="80629-127">Click **More Information** to get details of the activity.</span></span> <span data-ttu-id="80629-128">IsAdminContent が True に設定されている場合を確認します。</span><span class="sxs-lookup"><span data-stu-id="80629-128">Check to see if IsAdminContent is set to True.</span></span>

> [!NOTE]
>
> <span data-ttu-id="80629-129">イベントが発生した後、対応する監査ログ エントリが検索結果に表示されるには、最大 30 分から 24 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="80629-129">It can take from 30 minutes up to 24 hours for the corresponding audit log entry to be displayed in the search results after an event occurs.</span></span>
>
> <span data-ttu-id="80629-130">監査レコードが監査ログに保持および検索可能な期間は、Microsoft 365 サブスクリプション、特に特定のユーザーに割り当てられているライセンスの種類によって異なります。</span><span class="sxs-lookup"><span data-stu-id="80629-130">The length of time that an audit record is retained and searchable in the audit log depends on your Microsoft 365 subscription, and specifically the type of the license that is assigned to a specific user.</span></span> <span data-ttu-id="80629-131">詳細については、「監査ログ」 [を参照してください](../../compliance/search-the-audit-log-in-security-and-compliance.md)。</span><span class="sxs-lookup"><span data-stu-id="80629-131">For more information, see [Audit log](../../compliance/search-the-audit-log-in-security-and-compliance.md).</span></span>
>
> <span data-ttu-id="80629-132">この値が true の場合、グローバル管理者アクセス権を持つユーザーがデータへの広範なアクセスを許可した可能性があります。</span><span class="sxs-lookup"><span data-stu-id="80629-132">If this value is true, it indicates that someone with Global Administrator access may have granted broad access to data.</span></span> <span data-ttu-id="80629-133">予期しない場合は、攻撃を確認 [する手順を実行します](#how-to-confirm-an-attack)。</span><span class="sxs-lookup"><span data-stu-id="80629-133">If this is unexpected, take steps to [confirm an attack](#how-to-confirm-an-attack).</span></span>

## <a name="how-to-confirm-an-attack"></a><span data-ttu-id="80629-134">攻撃を確認する方法</span><span class="sxs-lookup"><span data-stu-id="80629-134">How to confirm an attack</span></span>

<span data-ttu-id="80629-135">上記の IOC のインスタンスが 1 つ以上ある場合は、攻撃が発生したことを肯定的に確認するために、さらに調査を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="80629-135">If you have one or more instances of the IOCs listed above, you need to do further investigation to positively confirm that the attack occurred.</span></span> <span data-ttu-id="80629-136">攻撃を確認するには、次の 3 つの方法を使用できます。</span><span class="sxs-lookup"><span data-stu-id="80629-136">You can use any of these three methods to confirm the attack:</span></span>

- <span data-ttu-id="80629-137">Azure Active Directory ポータルを使用したインベントリ アプリケーションとそのアクセス許可。</span><span class="sxs-lookup"><span data-stu-id="80629-137">Inventory applications and their permissions using the Azure Active Directory portal.</span></span> <span data-ttu-id="80629-138">この方法は十分ですが、一度に確認できるユーザーは 1 人のみです。多くのユーザーが確認できる場合は、非常に時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="80629-138">This method is thorough, but you can only check one user at a time which can be very time consuming if you have many users to check.</span></span>

- <span data-ttu-id="80629-139">PowerShell を使用してアプリケーションとそのアクセス許可をインベントリします。</span><span class="sxs-lookup"><span data-stu-id="80629-139">Inventory applications and their permissions using PowerShell.</span></span> <span data-ttu-id="80629-140">これは最も速く、最も徹底的な方法であり、オーバーヘッドは最小です。</span><span class="sxs-lookup"><span data-stu-id="80629-140">This is the fastest and most thorough method, with the least amount of overhead.</span></span>

- <span data-ttu-id="80629-141">ユーザーにアプリとアクセス許可を個別に確認し、結果を管理者に報告して修復を行います。</span><span class="sxs-lookup"><span data-stu-id="80629-141">Have your users individually check their apps and permissions and report the results back to the administrators for remediation.</span></span>

## <a name="inventory-apps-with-access-in-your-organization"></a><span data-ttu-id="80629-142">組織内のアクセス権を持つインベントリ アプリ</span><span class="sxs-lookup"><span data-stu-id="80629-142">Inventory apps with access in your organization</span></span>

<span data-ttu-id="80629-143">Azure Active Directory Portal または PowerShell を使用してユーザーに対してこれを行うか、ユーザーにアプリケーション アクセスを個別に列挙することができます。</span><span class="sxs-lookup"><span data-stu-id="80629-143">You can do this for your users with either the Azure Active Directory Portal, or PowerShell or have your users individually enumerate their application access.</span></span>

### <a name="steps-for-using-the-azure-active-directory-portal"></a><span data-ttu-id="80629-144">Azure Active Directory ポータルを使用する手順</span><span class="sxs-lookup"><span data-stu-id="80629-144">Steps for using the Azure Active Directory Portal</span></span>

<span data-ttu-id="80629-145">Azure Active Directory Portal を使用して、個々のユーザーがアクセス許可を付与したアプリケーション [を検索できます](https://portal.azure.com/)。</span><span class="sxs-lookup"><span data-stu-id="80629-145">You can look up the applications to which any individual user has granted permissions by using the [Azure Active Directory Portal](https://portal.azure.com/).</span></span>

1. <span data-ttu-id="80629-146">管理者権限を持つ Azure Portal にサインインします。</span><span class="sxs-lookup"><span data-stu-id="80629-146">Sign in to the Azure Portal with administrative rights.</span></span>

2. <span data-ttu-id="80629-147">[Azure Active Directory] ブレードを選択します。</span><span class="sxs-lookup"><span data-stu-id="80629-147">Select the Azure Active Directory blade.</span></span>

3. <span data-ttu-id="80629-148">[**ユーザー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="80629-148">Select **Users**.</span></span>

4. <span data-ttu-id="80629-149">確認するユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="80629-149">Select the user that you want to review.</span></span>

5. <span data-ttu-id="80629-150">[アプリケーション **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="80629-150">Select **Applications**.</span></span>

<span data-ttu-id="80629-151">これにより、ユーザーに割り当てられているアプリと、アプリケーションに与えるアクセス許可が表示されます。</span><span class="sxs-lookup"><span data-stu-id="80629-151">This will show you the apps that are assigned to the user and what permissions the applications have.</span></span>

### <a name="steps-for-having-your-users-enumerate-their-application-access"></a><span data-ttu-id="80629-152">ユーザーがアプリケーション アクセスを列挙する手順</span><span class="sxs-lookup"><span data-stu-id="80629-152">Steps for having your users enumerate their application access</span></span>

<span data-ttu-id="80629-153">ユーザーにアクセスして、 https://myapps.microsoft.com 自分のアプリケーション アクセスを確認します。</span><span class="sxs-lookup"><span data-stu-id="80629-153">Have your users go to https://myapps.microsoft.com and review their own application access there.</span></span> <span data-ttu-id="80629-154">アクセス権を持つすべてのアプリを表示し、そのアプリに関する詳細 (アクセス範囲を含む) を表示し、疑わしいアプリや不正なアプリに対する特権を取り消す必要があります。</span><span class="sxs-lookup"><span data-stu-id="80629-154">They should be able to see all the apps with access, view details about them (including the scope of access), and be able to revoke privileges to suspicious or illicit apps.</span></span>

### <a name="steps-for-doing-this-with-powershell"></a><span data-ttu-id="80629-155">PowerShell でこれを行う手順</span><span class="sxs-lookup"><span data-stu-id="80629-155">Steps for doing this with PowerShell</span></span>

<span data-ttu-id="80629-156">Illicit Consent Grant 攻撃を確認する最も簡単な方法は [ 、Get-AzureADPSPermissions.ps1](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09)を実行することです。これは、テナント内のすべてのユーザーに対してすべての OAuth 同意許可と OAuth アプリを 1 つの .csv ファイルにダンプします。</span><span class="sxs-lookup"><span data-stu-id="80629-156">The simplest way to verify the Illicit Consent Grant attack is to run [Get-AzureADPSPermissions.ps1](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09), which will dump all the OAuth consent grants and OAuth apps for all users in your tenancy into one .csv file.</span></span>

#### <a name="pre-requisites"></a><span data-ttu-id="80629-157">前提条件</span><span class="sxs-lookup"><span data-stu-id="80629-157">Pre-requisites</span></span>

- <span data-ttu-id="80629-158">Azure AD PowerShell ライブラリがインストールされています。</span><span class="sxs-lookup"><span data-stu-id="80629-158">The Azure AD PowerShell library installed.</span></span>

- <span data-ttu-id="80629-159">スクリプトが実行されるテナントのグローバル管理者権限。</span><span class="sxs-lookup"><span data-stu-id="80629-159">Global administrator rights on the tenant that the script will be run against.</span></span>

- <span data-ttu-id="80629-160">スクリプトを実行するコンピューターのローカル管理者。</span><span class="sxs-lookup"><span data-stu-id="80629-160">Local Administrator on the computer from which will run the scripts.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="80629-161">管理 ***アカウントで*** 多要素認証を必要とすることを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="80629-161">We ***highly recommend*** that you require multi-factor authentication on your administrative account.</span></span> <span data-ttu-id="80629-162">このスクリプトは MFA 認証をサポートします。</span><span class="sxs-lookup"><span data-stu-id="80629-162">This script supports MFA authentication.</span></span>

1. <span data-ttu-id="80629-163">ローカル管理者権限でスクリプトを実行するコンピューターにサインインします。</span><span class="sxs-lookup"><span data-stu-id="80629-163">Sign in to the computer that you will run the script from with local administrator rights.</span></span>

2. <span data-ttu-id="80629-164">GitHub からスクリプト [Get-AzureADPSPermissions.ps1](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09) スクリプトを実行するフォルダーにダウンロードまたはコピーします。</span><span class="sxs-lookup"><span data-stu-id="80629-164">Download or copy the [Get-AzureADPSPermissions.ps1](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09) script from GitHub to a folder from which you will run the script.</span></span> <span data-ttu-id="80629-165">これは、出力 "permissions.csv" ファイルが書き込まれるのと同じフォルダーです。</span><span class="sxs-lookup"><span data-stu-id="80629-165">This will be the same folder to which the output "permissions.csv" file will be written.</span></span>

3. <span data-ttu-id="80629-166">PowerShell インスタンスを管理者として開き、スクリプトを保存したフォルダーを開きます。</span><span class="sxs-lookup"><span data-stu-id="80629-166">Open a PowerShell instance as an administrator and open to the folder you saved the script to.</span></span>

4. <span data-ttu-id="80629-167">[Connect-AzureAD コマンドレットを使用してディレクトリに接続](/powershell/module/azuread/connect-azuread)します。</span><span class="sxs-lookup"><span data-stu-id="80629-167">Connect to your directory using the [Connect-AzureAD](/powershell/module/azuread/connect-azuread) cmdlet.</span></span>

5. <span data-ttu-id="80629-168">次の PowerShell コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="80629-168">Run this PowerShell command:</span></span>

   ```powershell
   Get-AzureADPSPermissions.ps1 | Export-csv -Path "Permissions.csv" -NoTypeInformation
   ```

<span data-ttu-id="80629-169">スクリプトは、1 つのファイルを Permissions.csv。</span><span class="sxs-lookup"><span data-stu-id="80629-169">The script produces one file named Permissions.csv.</span></span> <span data-ttu-id="80629-170">次の手順に従って、不正なアプリケーションのアクセス許可の付与を探します。</span><span class="sxs-lookup"><span data-stu-id="80629-170">Follow these steps to look for illicit application permission grants:</span></span>

1. <span data-ttu-id="80629-171">ConsentType 列 (列 G) で値 "AllPrinciples" を検索します。</span><span class="sxs-lookup"><span data-stu-id="80629-171">In the ConsentType column (column G) search for the value "AllPrinciples".</span></span> <span data-ttu-id="80629-172">AllPrincipals アクセス許可を使用すると、クライアント アプリケーションはテナンシー内のすべてのユーザーのコンテンツにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="80629-172">The AllPrincipals permission allows the client application to access everyone's content in the tenancy.</span></span> <span data-ttu-id="80629-173">ネイティブ Microsoft 365 アプリケーションでは、このアクセス許可を正しく動作する必要があります。</span><span class="sxs-lookup"><span data-stu-id="80629-173">Native Microsoft 365 applications need this permission to work correctly.</span></span> <span data-ttu-id="80629-174">このアクセス許可を持つ Microsoft 以外のすべてのアプリケーションは、慎重に確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="80629-174">Every non-Microsoft application with this permission should be reviewed carefully.</span></span>

2. <span data-ttu-id="80629-175">[アクセス許可] 列 (列 F) で、委任された各アプリケーションがコンテンツに対して持つアクセス許可を確認します。</span><span class="sxs-lookup"><span data-stu-id="80629-175">In the Permission column (column F) review the permissions that each delegated application has to content.</span></span> <span data-ttu-id="80629-176">"読み取り" および "書き込み" アクセス許可または "\*" を探します。[すべて] アクセス許可を使用し、適切ではない可能性があるから、これらを慎重に確認します。</span><span class="sxs-lookup"><span data-stu-id="80629-176">Look for "Read" and "Write" permission or "\*.All" permission, and review these carefully because they may not be appropriate.</span></span>

3. <span data-ttu-id="80629-177">同意が付与されている特定のユーザーを確認します。</span><span class="sxs-lookup"><span data-stu-id="80629-177">Review the specific users that have consents granted.</span></span> <span data-ttu-id="80629-178">高プロファイルまたは影響の大きなユーザーに不適切な同意が付与されている場合は、さらに調査する必要があります。</span><span class="sxs-lookup"><span data-stu-id="80629-178">If high profile or high impact users have inappropriate consents granted, you should investigate further.</span></span>

4. <span data-ttu-id="80629-179">[ClientDisplayName] 列 (列 C) で、疑わしいと思われるアプリを探します。</span><span class="sxs-lookup"><span data-stu-id="80629-179">In the ClientDisplayName column (column C) look for apps that seem suspicious.</span></span> <span data-ttu-id="80629-180">スペルミスの名前、スーパーブランド名、またはハッカーサウンドの名前を持つアプリは、慎重に検討する必要があります。</span><span class="sxs-lookup"><span data-stu-id="80629-180">Apps with misspelled names, super bland names, or hacker-sounding names should be reviewed carefully.</span></span>

## <a name="determine-the-scope-of-the-attack"></a><span data-ttu-id="80629-181">攻撃の範囲を特定する</span><span class="sxs-lookup"><span data-stu-id="80629-181">Determine the scope of the attack</span></span>

<span data-ttu-id="80629-182">アプリケーション アクセスのインベントリが完了したら、監査ログを **確認して** 侵害の全範囲を特定します。</span><span class="sxs-lookup"><span data-stu-id="80629-182">After you have finished inventorying application access, review the **audit log** to determine the full scope of the breach.</span></span> <span data-ttu-id="80629-183">影響を受けるユーザー、不正なアプリケーションが組織にアクセスしたタイム フレーム、およびアプリが持っていたアクセス許可を検索します。</span><span class="sxs-lookup"><span data-stu-id="80629-183">Search on the affected users, the time frames that the illicit application had access to your organization, and the permissions the app had.</span></span> <span data-ttu-id="80629-184">監査ログは **、Microsoft** [365 セキュリティ/コンプライアンス センターで検索できます](../../compliance/search-the-audit-log-in-security-and-compliance.md)。</span><span class="sxs-lookup"><span data-stu-id="80629-184">You can search the **audit log** in the [Microsoft 365 Security and Compliance Center](../../compliance/search-the-audit-log-in-security-and-compliance.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="80629-185">[この情報を取得](../../compliance/enable-mailbox-auditing.md)するには、管理者とユーザーのメールボックス監査とアクティビティ監査が攻撃の前に有効になっている必要があります。 [](../../compliance/turn-audit-log-search-on-or-off.md)</span><span class="sxs-lookup"><span data-stu-id="80629-185">[Mailbox auditing](../../compliance/enable-mailbox-auditing.md) and [Activity auditing for admins and users](../../compliance/turn-audit-log-search-on-or-off.md) must have been enabled prior to the attack for you to get this information.</span></span>

## <a name="how-to-stop-and-remediate-an-illicit-consent-grant-attack"></a><span data-ttu-id="80629-186">不正な同意許可攻撃を停止して修復する方法</span><span class="sxs-lookup"><span data-stu-id="80629-186">How to stop and remediate an illicit consent grant attack</span></span>

<span data-ttu-id="80629-187">不正なアクセス許可を持つアプリケーションを特定した後、そのアクセスを削除する方法がいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="80629-187">After you have identified an application with illicit permissions, you have several ways to remove that access.</span></span>

- <span data-ttu-id="80629-188">Azure Active Directory Portal でアプリケーションのアクセス許可を取り消す方法は、次の方法で行います。</span><span class="sxs-lookup"><span data-stu-id="80629-188">You can revoke the application's permission in the Azure Active Directory Portal by:</span></span>

  - <span data-ttu-id="80629-189">[Azure Active Directory ユーザー] ブレードで、影響 **を受けるユーザーに移動** します。</span><span class="sxs-lookup"><span data-stu-id="80629-189">Navigate to the affected user in the **Azure Active Directory User** blade.</span></span>

  - <span data-ttu-id="80629-190">[アプリケーション **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="80629-190">Select **Applications**.</span></span>

  - <span data-ttu-id="80629-191">不正なアプリケーションを選択します。</span><span class="sxs-lookup"><span data-stu-id="80629-191">Select the illicit application.</span></span>

  - <span data-ttu-id="80629-192">ドリルダウン **で [削除** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="80629-192">Click **Remove** in the drill down.</span></span>

- <span data-ttu-id="80629-193">[Remove-AzureADOAuth2PermissionGrant](/powershell/module/azuread/Remove-AzureADOAuth2PermissionGrant)の手順に従って、PowerShell で OAuth 同意付与を取り消します。</span><span class="sxs-lookup"><span data-stu-id="80629-193">You can revoke the OAuth consent grant with PowerShell by following the steps in [Remove-AzureADOAuth2PermissionGrant](/powershell/module/azuread/Remove-AzureADOAuth2PermissionGrant).</span></span>

- <span data-ttu-id="80629-194">[Remove-AzureADServiceAppRoleAssignment](/powershell/module/azuread/Remove-AzureADServiceAppRoleAssignment)の手順に従って、PowerShell を使用してサービス アプリの役割の割り当てを取り消します。</span><span class="sxs-lookup"><span data-stu-id="80629-194">You can revoke the Service App Role Assignment with PowerShell by following the steps in [Remove-AzureADServiceAppRoleAssignment](/powershell/module/azuread/Remove-AzureADServiceAppRoleAssignment).</span></span>

- <span data-ttu-id="80629-195">また、影響を受けるアカウントのサインインを完全に無効にすることもできます。この場合、そのアカウントのデータへのアプリ アクセスが無効になります。</span><span class="sxs-lookup"><span data-stu-id="80629-195">You can also disable sign-in for the affected account altogether, which will in turn disable app access to data in that account.</span></span> <span data-ttu-id="80629-196">もちろん、これはエンド ユーザーの生産性にとって理想的な方法ではありません。ただし、影響を迅速に制限するために作業している場合、実行可能な短期的な修復になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="80629-196">This isn't ideal for the end user's productivity, of course, but if you are working to limit impact quickly, it can be a viable short-term remediation.</span></span>

- <span data-ttu-id="80629-197">テナンシーのために統合アプリケーションをオフにできます。</span><span class="sxs-lookup"><span data-stu-id="80629-197">You can turn integrated applications off for your tenancy.</span></span> <span data-ttu-id="80629-198">これは、エンド ユーザーがテナント全体で同意を付与する機能を無効にする抜本的な手順です。</span><span class="sxs-lookup"><span data-stu-id="80629-198">This is a drastic step that disables the ability for end users to grant consent on a tenant-wide basis.</span></span> <span data-ttu-id="80629-199">これにより、ユーザーが悪意のあるアプリケーションへのアクセスを誤って許可するのを防ぐことが可能です。</span><span class="sxs-lookup"><span data-stu-id="80629-199">This prevents your users from inadvertently granting access to a malicious application.</span></span> <span data-ttu-id="80629-200">これは、ユーザーがサードパーティ アプリケーションで生産性を向上する能力を著しく損なうので、強く推奨されません。</span><span class="sxs-lookup"><span data-stu-id="80629-200">This isn't strongly recommended as it severely impairs your users' ability to be productive with third party applications.</span></span> <span data-ttu-id="80629-201">これを行うには、「統合アプリをオンまたはオフにする」 [の手順に従います](../../admin/misc/user-consent.md)。</span><span class="sxs-lookup"><span data-stu-id="80629-201">You can do this by following the steps in [Turning Integrated Apps on or off](../../admin/misc/user-consent.md).</span></span>

## <a name="secure-microsoft-365-like-a-cybersecurity-pro"></a><span data-ttu-id="80629-202">サイバー セキュリティの専門家のように、Microsoft 365 のセキュリティを強化する</span><span class="sxs-lookup"><span data-stu-id="80629-202">Secure Microsoft 365 like a cybersecurity pro</span></span>

<span data-ttu-id="80629-203">Microsoft 365 サブスクリプションには、データとユーザーを保護するために使用できる強力なセキュリティ機能のセットが用意されています。</span><span class="sxs-lookup"><span data-stu-id="80629-203">Your Microsoft 365 subscription comes with a powerful set of security capabilities that you can use to protect your data and your users.</span></span> <span data-ttu-id="80629-204">[Microsoft 365 セキュリティ ロードマップ - 最初の 30 日間、90 日間、およびそれ以降の最優先事項](security-roadmap.md)を使用して、Microsoft 365 テナントをセキュリティで保護するために Microsoft が推奨するベスト プラクティスを実装します。</span><span class="sxs-lookup"><span data-stu-id="80629-204">Use the [Microsoft 365 security roadmap - Top priorities for the first 30 days, 90 days, and beyond](security-roadmap.md) to implement Microsoft recommended best practices for securing your Microsoft 365 tenant.</span></span>

- <span data-ttu-id="80629-205">最初の 30 日間に実行するタスク。</span><span class="sxs-lookup"><span data-stu-id="80629-205">Tasks to accomplish in the first 30 days.</span></span> <span data-ttu-id="80629-206">これらは直ちに影響を及ぼし、ユーザーに対する影響は低いです。</span><span class="sxs-lookup"><span data-stu-id="80629-206">These have immediate affect and are low-impact to your users.</span></span>

- <span data-ttu-id="80629-p123">最初の 90 日間で完了すべき作業。作業の計画と実装に少し時間がかかりますが、セキュリティ体制は大幅に向上します。</span><span class="sxs-lookup"><span data-stu-id="80629-p123">Tasks to accomplish in 90 days. These take a bit more time to plan and implement but greatly improve your security posture.</span></span>

- <span data-ttu-id="80629-p124">90 日以降。最初の 90 日間の作業で保護が強化されます。</span><span class="sxs-lookup"><span data-stu-id="80629-p124">Beyond 90 days. These enhancements build in your first 90 days work.</span></span>

## <a name="see-also"></a><span data-ttu-id="80629-211">関連項目:</span><span class="sxs-lookup"><span data-stu-id="80629-211">See also:</span></span>

- <span data-ttu-id="80629-212">[[アプリケーション] リストの予期しない](/azure/active-directory/application-access-unexpected-application) アプリケーションは、データにアクセスできる予期しないアプリケーションが発生した後に、管理者が実行する必要があるさまざまなアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="80629-212">[Unexpected application in my applications list](/azure/active-directory/application-access-unexpected-application) walks administrators through various actions they may want to take after realizing there are unexpected applications with access to data.</span></span>

- <span data-ttu-id="80629-213">[アプリケーションと Azure Active Directory の統合](/azure/active-directory/active-directory-apps-permissions-consent) は、同意とアクセス許可の概要です。</span><span class="sxs-lookup"><span data-stu-id="80629-213">[Integrating applications with Azure Active Directory](/azure/active-directory/active-directory-apps-permissions-consent) is a high-level overview of consent and permissions.</span></span>

- <span data-ttu-id="80629-214">[アプリケーションの開発に関する問題は、](/azure/active-directory/active-directory-application-dev-development-content-map) さまざまな同意関連記事へのリンクを提供します。</span><span class="sxs-lookup"><span data-stu-id="80629-214">[Problems developing my application](/azure/active-directory/active-directory-application-dev-development-content-map) provides links to various consent related articles.</span></span>

- <span data-ttu-id="80629-215">[Azure Active Directory (Azure AD)](/azure/active-directory/develop/active-directory-application-objects) のアプリケーション プリンシパル オブジェクトとサービス プリンシパル オブジェクトは、アプリケーション モデルの中核となる Application および Service プリンシパル オブジェクトの概要を示します。</span><span class="sxs-lookup"><span data-stu-id="80629-215">[Application and service principal objects in Azure Active Directory (Azure AD)](/azure/active-directory/develop/active-directory-application-objects) provides an overview of the Application and Service principal objects that are core to the application model.</span></span>

- <span data-ttu-id="80629-216">[アプリへのアクセスの管理](/azure/active-directory/active-directory-managing-access-to-apps) は、管理者がアプリへのユーザー アクセスを管理する必要がある機能の概要です。</span><span class="sxs-lookup"><span data-stu-id="80629-216">[Manage access to apps](/azure/active-directory/active-directory-managing-access-to-apps) is an overview of the capabilities that administrators have to manage user access to apps.</span></span>