---
title: Microsoft Office 365 での不正な同意付与の検出と修復
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.collection:
- o365_security_incident_response
- M365-security-compliance
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
description: Office 365 で不法な同意を付与する攻撃を認識し、修復する方法について説明します。
ms.openlocfilehash: 0f4569a4ef8496a07fc1dc52f500ee91a6590fdd
ms.sourcegitcommit: 3063e351e21614c236167e9cde40994d8b532bd6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/08/2020
ms.locfileid: "40989542"
---
# <a name="detect-and-remediate-illicit-consent-grants-in-office-365"></a><span data-ttu-id="6f85e-103">Microsoft Office 365 での不正な同意付与の検出と修復</span><span class="sxs-lookup"><span data-stu-id="6f85e-103">Detect and Remediate Illicit Consent Grants in Office 365</span></span>

<span data-ttu-id="6f85e-104">**概要** Office 365 で不法な同意を付与する攻撃を認識し、修復する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="6f85e-104">**Summary**  Learn how to recognize and remediate the illicit consent grants attack in Office 365.</span></span>

## <a name="what-is-the-illicit-consent-grant-attack-in-office-365"></a><span data-ttu-id="6f85e-105">Office 365 における不正な同意の付与攻撃</span><span class="sxs-lookup"><span data-stu-id="6f85e-105">What is the illicit consent grant attack in Office 365?</span></span>

<span data-ttu-id="6f85e-106">違法同意付与攻撃では、攻撃者は、連絡先情報、電子メール、ドキュメントなどのデータへのアクセスを要求する Azure 登録済みアプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="6f85e-106">In an illicit consent grant attack, the attacker creates an Azure-registered application that requests access to data such as contact information, email, or documents.</span></span> <span data-ttu-id="6f85e-107">その後、攻撃者はエンドユーザーに対して、フィッシング攻撃によるデータへのアクセスを許可するように指示するか、または信頼された web サイトに不法なコードを挿入します。</span><span class="sxs-lookup"><span data-stu-id="6f85e-107">The attacker then tricks an end user into granting that application consent to access their data either through a phishing attack, or by injecting illicit code into a trusted website.</span></span> <span data-ttu-id="6f85e-108">不正なアプリケーションに同意した後は、組織のアカウントを使用しなくても、データへのアカウントレベルのアクセス権が付与されます。</span><span class="sxs-lookup"><span data-stu-id="6f85e-108">After the illicit application has been granted consent, it has account-level access to data without the need for an organizational account.</span></span> <span data-ttu-id="6f85e-109">違反アカウントのパスワードをリセットしたり、アカウントに多要素認証 (MFA) を必要としたりするなど、通常の修復手順は、この種の攻撃に対しては有効ではありません。これらはサードパーティのアプリケーションであり、組織の外部にあるためです。</span><span class="sxs-lookup"><span data-stu-id="6f85e-109">Normal remediation steps, like resetting passwords for breached accounts or requiring Multi-Factor Authentication (MFA) on accounts, are not effective against this type of attack, since these are third-party applications and are external to the organization.</span></span> <span data-ttu-id="6f85e-110">これらの攻撃は、情報を呼び出しているエンティティが人間ではなく、オートメーションであることを前提とする相互作用モデルを利用します。</span><span class="sxs-lookup"><span data-stu-id="6f85e-110">These attacks leverage an interaction model which presumes the entity that is calling the information is automation and not a human.</span></span>

## <a name="what-does-an-illicit-consent-grant-attack-look-like-in-office-365"></a><span data-ttu-id="6f85e-111">Office 365 のように、不法な同意を与える攻撃はどのようになりますか?</span><span class="sxs-lookup"><span data-stu-id="6f85e-111">What does an illicit consent grant attack look like in Office 365?</span></span>

<span data-ttu-id="6f85e-112">この攻撃の兆候 (IOC) を検出するには、Office 365**監査ログ**を検索する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6f85e-112">You need to search the Office 365 **audit log** to find signs, also called Indicators of Compromise (IOC) of this attack.</span></span> <span data-ttu-id="6f85e-113">Azure に登録されているアプリケーションの数が多く、ユーザーが大規模な組織では、組織の同意の付与を週単位で確認することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6f85e-113">For organizations with many Azure-registered applications and a large user base, the best practice is to review your organizations consent grants on a weekly basis.</span></span>

### <a name="steps-for-finding-signs-of-this-attack"></a><span data-ttu-id="6f85e-114">この攻撃の兆候を見つけるための手順</span><span class="sxs-lookup"><span data-stu-id="6f85e-114">Steps for finding signs of this attack</span></span>

1. <span data-ttu-id="6f85e-115">Office 365 テナントの [**セキュリティとコンプライアンスセンター** ] を開きます。</span><span class="sxs-lookup"><span data-stu-id="6f85e-115">Open the **Security and Compliance Center** in your Office 365 tenant.</span></span>

2. <span data-ttu-id="6f85e-116">[**検索 & 調査**] ノードに移動して、[**監査ログ**の検索] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6f85e-116">Navigate to the **Search & investigation** node and select **audit log** search.</span></span>

3. <span data-ttu-id="6f85e-117">検索を作成し (すべてのアクティビティとすべてのユーザー)、アプリケーションに対する同意のために結果をフィルター処理して、OAuth2PermissionGrant を追加します。</span><span class="sxs-lookup"><span data-stu-id="6f85e-117">Create a search (all activities and all users) and filter the results for Consent to application, and Add OAuth2PermissionGrant.</span></span>

4. <span data-ttu-id="6f85e-118">拡張プロパティを調べ、IsAdminContent が True に設定されているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="6f85e-118">Examine the Extended Properties and check to see if IsAdminContent is set to True.</span></span>

> [!NOTE]
> <span data-ttu-id="6f85e-119">•対応する監査ログエントリが検索結果に表示されるまでに、イベントが発生した後、最大30分または最大24時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="6f85e-119">• It can take up to 30 minutes or up to 24 hours after an event occurs for the corresponding audit log entry to be displayed in the search results.</span></span> <br/><br/> <span data-ttu-id="6f85e-120">•監査レコードが保持され、監査ログで検索可能になる時間の長さは、Office 365 のサブスクリプション、および特定のユーザーに割り当てられているライセンスの種類によって異なります。</span><span class="sxs-lookup"><span data-stu-id="6f85e-120">• The length of time that an audit record is retained and searchable in the audit log depends on your Office 365 subscription, and specifically the type of the license that is assigned to a specific user.</span></span> <span data-ttu-id="6f85e-121">詳細については、「[監査ログ](../../compliance/search-the-audit-log-in-security-and-compliance.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6f85e-121">For more information, see [Audit log](../../compliance/search-the-audit-log-in-security-and-compliance.md).</span></span>
<span data-ttu-id="6f85e-122">この値が true の場合は、グローバル管理者のアクセス権を持つユーザーがデータへの広範なアクセス権を持っている可能性があることを示します。</span><span class="sxs-lookup"><span data-stu-id="6f85e-122">If this value is true, it indicates that someone with Global Administrator access may have granted broad access to data.</span></span> <span data-ttu-id="6f85e-123">これが予期しない場合は、[攻撃を確認](#how-to-confirm-an-attack)するための手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="6f85e-123">If this is unexpected, take steps to [confirm an attack](#how-to-confirm-an-attack).</span></span>

## <a name="how-to-confirm-an-attack"></a><span data-ttu-id="6f85e-124">攻撃を確認する方法</span><span class="sxs-lookup"><span data-stu-id="6f85e-124">How to confirm an attack</span></span>

<span data-ttu-id="6f85e-125">上記の IOCs のインスタンスが1つ以上ある場合は、攻撃が発生したことを確認するためにさらに調査する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6f85e-125">If you have one or more instances of the IOCs listed above, you need to do further investigation to positively confirm that the attack occurred.</span></span> <span data-ttu-id="6f85e-126">これら3つの方法のいずれかを使用して、攻撃を確認できます。</span><span class="sxs-lookup"><span data-stu-id="6f85e-126">You can use any of these three methods to confirm the attack.</span></span>

- <span data-ttu-id="6f85e-127">Azure Active Directory ポータルを使用した、アプリケーションとそのアクセス許可の一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="6f85e-127">Inventory applications and their permissions using the Azure Active Directory portal.</span></span> <span data-ttu-id="6f85e-128">この方法は徹底していますが、チェックするユーザーが多い場合は、一度に1人のユーザーをチェックするだけで十分な時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="6f85e-128">This method is thorough, but you can only check one user at a time which can be very time consuming if you have many users to check.</span></span>

- <span data-ttu-id="6f85e-129">PowerShell を使用した、アプリケーションとそのアクセス許可の一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="6f85e-129">Inventory applications and their permissions using PowerShell.</span></span> <span data-ttu-id="6f85e-130">これは、最も少ないオーバーヘッドを最小限にした最も高速かつ最も綿密な方法です。</span><span class="sxs-lookup"><span data-stu-id="6f85e-130">This is the fastest and most thorough method, with the least amount of overhead.</span></span>

- <span data-ttu-id="6f85e-131">ユーザーが自分のアプリとアクセス許可を個別に確認して、修復のために管理者に結果を報告するようにします。</span><span class="sxs-lookup"><span data-stu-id="6f85e-131">Have your users individually check their apps and permissions and report the results back to the administrators for remediation.</span></span>

## <a name="inventory-apps-with-access-in-your-organization"></a><span data-ttu-id="6f85e-132">組織内でアクセスできるインベントリアプリ</span><span class="sxs-lookup"><span data-stu-id="6f85e-132">Inventory apps with access in your organization</span></span>

<span data-ttu-id="6f85e-133">これは、Azure Active Directory ポータルまたは PowerShell を使用しているユーザーに対して行うことができます。または、ユーザーがアプリケーションアクセスを個別に列挙する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6f85e-133">You can do this for your users with either the Azure Active Directory Portal, or PowerShell or have your users individually enumerate their application access.</span></span>

### <a name="steps-for-using-the-azure-active-directory-portal"></a><span data-ttu-id="6f85e-134">Azure Active Directory ポータルを使用するための手順</span><span class="sxs-lookup"><span data-stu-id="6f85e-134">Steps for using the Azure Active Directory Portal</span></span>

<span data-ttu-id="6f85e-135">[Azure Active Directory ポータル](https://portal.azure.com/)を使用して、個々のユーザーがアクセス許可を付与したアプリケーションを検索できます。</span><span class="sxs-lookup"><span data-stu-id="6f85e-135">You can look up the applications to which any individual user has granted permissions by using the [Azure Active Directory Portal](https://portal.azure.com/).</span></span>

1. <span data-ttu-id="6f85e-136">管理者権限を使用して Azure Portal にサインインします。</span><span class="sxs-lookup"><span data-stu-id="6f85e-136">Sign in to the Azure Portal with administrative rights.</span></span>

2. <span data-ttu-id="6f85e-137">Azure Active Directory ブレードを選択します。</span><span class="sxs-lookup"><span data-stu-id="6f85e-137">Select the Azure Active Directory blade.</span></span>

3. <span data-ttu-id="6f85e-138">[**ユーザー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6f85e-138">Select **Users**.</span></span>

4. <span data-ttu-id="6f85e-139">確認するユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="6f85e-139">Select the user that you want to review.</span></span>

5. <span data-ttu-id="6f85e-140">[**アプリケーション**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6f85e-140">Select **Applications**.</span></span>

<span data-ttu-id="6f85e-141">これにより、ユーザーに割り当てられているアプリと、applcations に設定されているアクセス許可が表示されます。</span><span class="sxs-lookup"><span data-stu-id="6f85e-141">This will show you the apps that are assigned to the user and what permissions the applcations have.</span></span>

### <a name="steps-for-having-your-users-enumerate-their-application-access"></a><span data-ttu-id="6f85e-142">ユーザーがアプリケーションアクセスを列挙する手順</span><span class="sxs-lookup"><span data-stu-id="6f85e-142">Steps for having your users enumerate their application access</span></span>

<span data-ttu-id="6f85e-143">ユーザーが自分のアプリケーションhttps://myapps.microsoft.comへのアクセスを確認してもらいます。</span><span class="sxs-lookup"><span data-stu-id="6f85e-143">Have your users go to https://myapps.microsoft.com and review their own application access there.</span></span> <span data-ttu-id="6f85e-144">これらのユーザーは、アクセス可能なすべてのアプリを表示したり、それらに関する詳細を表示したり (アクセスの範囲を含む)、疑わしいまたは不法なアプリに対して権限を取り消すことができます。</span><span class="sxs-lookup"><span data-stu-id="6f85e-144">They should be able to see all the apps with access, view details about them (including the scope of access), and be able to revoke privileges to suspicious or illicit apps.</span></span>

### <a name="steps-for-doing-this-with-powershell"></a><span data-ttu-id="6f85e-145">PowerShell を使用してこれを行うための手順</span><span class="sxs-lookup"><span data-stu-id="6f85e-145">Steps for doing this with PowerShell</span></span>

<span data-ttu-id="6f85e-146">不法同意付与攻撃を確認する最も簡単な方法は、 [Get-AzureADPSPermissions](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09)を実行することです。これにより、テナント内のすべてのユーザーの oauth 承諾許可と oauth アプリがすべて、1つの .csv ファイルにダンプされます。</span><span class="sxs-lookup"><span data-stu-id="6f85e-146">The simplest way to verify the Illicit Consent Grant attack is to run [Get-AzureADPSPermissions.ps1](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09), which will dump all the OAuth consent grants and OAuth apps for all users in your tenancy into one .csv file.</span></span>

#### <a name="pre-requisites"></a><span data-ttu-id="6f85e-147">前提条件</span><span class="sxs-lookup"><span data-stu-id="6f85e-147">Pre-requisites</span></span>

- <span data-ttu-id="6f85e-148">Azure AD PowerShell ライブラリがインストールされていること。</span><span class="sxs-lookup"><span data-stu-id="6f85e-148">The Azure AD PowerShell library installed.</span></span>

- <span data-ttu-id="6f85e-149">スクリプトが実行されるテナントのグローバル管理者権限。</span><span class="sxs-lookup"><span data-stu-id="6f85e-149">Global administrator rights on the tenant that the script will be run against.</span></span>

- <span data-ttu-id="6f85e-150">スクリプトを実行するコンピューターのローカル管理者。</span><span class="sxs-lookup"><span data-stu-id="6f85e-150">Local Administrator on the computer from which will run the scripts.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6f85e-151">管理アカウントでは、多要素認証を必要とすることを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6f85e-151">We highly recommend that you require multi-factor authentication on your administrative account.</span></span> <span data-ttu-id="6f85e-152">このスクリプトは、MFA 認証をサポートします。</span><span class="sxs-lookup"><span data-stu-id="6f85e-152">This script supports MFA authentication.</span></span>

1. <span data-ttu-id="6f85e-153">スクリプトを実行するコンピューターに、ローカル管理者権限を使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="6f85e-153">Sign in to the computer that you will run the script from with local administrator rights.</span></span>

2. <span data-ttu-id="6f85e-154">GitHub から scruipt を実行するフォルダーに[Get-AzureADPSPermissions](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09)スクリプトをダウンロードするか、コピーします。</span><span class="sxs-lookup"><span data-stu-id="6f85e-154">Download or copy the [Get-AzureADPSPermissions.ps1](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09) script from GitHub to a folder from which you will run the scruipt.</span></span> <span data-ttu-id="6f85e-155">これは、出力 "permissions" ファイルが書き込まれるフォルダーと同じです。</span><span class="sxs-lookup"><span data-stu-id="6f85e-155">This will be the same folder to which the output "permissions.csv" file will be written.</span></span>

3. <span data-ttu-id="6f85e-156">管理者として PowerShell インスタンスを開き、スクリプトを保存したフォルダーを開きます。</span><span class="sxs-lookup"><span data-stu-id="6f85e-156">Open a PowerShell instance as an administrator and open to the folder you saved the script to.</span></span>

4. <span data-ttu-id="6f85e-157">[AzureAD](https://docs.microsoft.com/powershell/module/azuread/connect-azuread)コマンドレットを使用して、ディレクトリに接続します。</span><span class="sxs-lookup"><span data-stu-id="6f85e-157">Connect to your directory using the [Connect-AzureAD](https://docs.microsoft.com/powershell/module/azuread/connect-azuread) cmdlet.</span></span>

5. <span data-ttu-id="6f85e-158">次の PowerShell コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="6f85e-158">Run this PowerShell command:</span></span>

   ```powershell
   Get-AzureADPSPermissions.ps1 | Export-csv -Path "Permissions.csv" -NoTypeInformation
   ```

<span data-ttu-id="6f85e-159">スクリプトによって、Permissions という名前のファイルが1つ作成されます。</span><span class="sxs-lookup"><span data-stu-id="6f85e-159">The script produces one file named Permissions.csv.</span></span> <span data-ttu-id="6f85e-160">次の手順に従って、不法なアプリケーションアクセス許可の付与を検索します。</span><span class="sxs-lookup"><span data-stu-id="6f85e-160">Follow these steps to look for illicit application permission grants:</span></span>

1. <span data-ttu-id="6f85e-161">[Conな種類] 列 (列 G) で、値 "AllPrinciples" を検索します。</span><span class="sxs-lookup"><span data-stu-id="6f85e-161">In the ConsentType column (column G) search for the value "AllPrinciples".</span></span> <span data-ttu-id="6f85e-162">AllPrincipals アクセス許可によって、クライアントアプリケーションは、テナント内のすべてのユーザーのコンテンツにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="6f85e-162">The AllPrincipals permission allows the client application to access everyone’s content in the tenancy.</span></span> <span data-ttu-id="6f85e-163">ネイティブの Office 365 アプリケーションは、正しく動作するためにこのアクセス許可を必要とします。</span><span class="sxs-lookup"><span data-stu-id="6f85e-163">Native Office 365 applications need this permission to work correctly.</span></span> <span data-ttu-id="6f85e-164">このアクセス許可を持つ Microsoft 以外のすべてのアプリケーションは、慎重にレビューする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6f85e-164">Every non-Microsoft application with this permission should be reviewed carefully.</span></span>

2. <span data-ttu-id="6f85e-165">[アクセス許可] 列 (列 F) に、各委任されたアプリケーションがコンテンツに対して持っているアクセス許可を確認します。</span><span class="sxs-lookup"><span data-stu-id="6f85e-165">In the Permission column (column F) review the permissions that each delegated application has to content.</span></span> <span data-ttu-id="6f85e-166">"読み取り" と "書き込み" アクセス許可または "\* を探します。All "アクセス許可を使用して、適切ではない可能性があるため慎重に確認してください。</span><span class="sxs-lookup"><span data-stu-id="6f85e-166">Look for "Read" and "Write" permission or "\*.All" permission, and review these carefully because they may not be appropriate.</span></span>

3. <span data-ttu-id="6f85e-167">同意が付与されている特定のユーザーを確認します。</span><span class="sxs-lookup"><span data-stu-id="6f85e-167">Review the specific users that have consents granted.</span></span> <span data-ttu-id="6f85e-168">プロファイルが大きい場合や、影響度の高いユーザーに不適切な同意が付与されている場合は、さらに詳しく調査する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6f85e-168">If high profile or high impact users have inappropriate consents granted, you should investigate further.</span></span>

4. <span data-ttu-id="6f85e-169">[ClientDisplayName] 列 (列 C) で、疑わしいと思われるアプリを探します。</span><span class="sxs-lookup"><span data-stu-id="6f85e-169">In the ClientDisplayName column (column C) look for apps that seem suspicious.</span></span> <span data-ttu-id="6f85e-170">名前のスペルが間違っているアプリ、super bland names、またはハッカーが発音した名前は、慎重に検討する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6f85e-170">Apps with misspelled names, super bland names, or hacker-sounding names should be reviewed carefully.</span></span>

## <a name="determine-the-scope-of-the-attack"></a><span data-ttu-id="6f85e-171">攻撃の範囲を決定する</span><span class="sxs-lookup"><span data-stu-id="6f85e-171">Determine the scope of the attack</span></span>

<span data-ttu-id="6f85e-172">アプリケーションアクセスのインベントリ処理が終了したら、Office 365**監査ログ**を確認して、違反の完全なスコープを特定します。</span><span class="sxs-lookup"><span data-stu-id="6f85e-172">After you have finished inventorying application access, review the Office 365 **audit log** to determine the full scope of the breach.</span></span> <span data-ttu-id="6f85e-173">影響を受けるユーザー、不法アプリケーションが組織にアクセスした時間枠、およびアプリのアクセス許可を検索します。</span><span class="sxs-lookup"><span data-stu-id="6f85e-173">Search on the affected users, the time frames that the illicit application had access to your organization, and the permissions the app had.</span></span> <span data-ttu-id="6f85e-174">**監査ログ**は、 [Microsoft 365 セキュリティ/コンプライアンスセンター](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)で検索できます。</span><span class="sxs-lookup"><span data-stu-id="6f85e-174">You can search the **audit log** in the [Microsoft 365 Security and Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6f85e-175">この情報を取得するには、攻撃の前に、[管理者とユーザーの](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off)[メールボックスの監査](https://docs.microsoft.com/microsoft-365/compliance/enable-mailbox-auditing)とアクティビティの監査を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6f85e-175">[Mailbox auditing](https://docs.microsoft.com/microsoft-365/compliance/enable-mailbox-auditing) and [Activity auditing for admins and users](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off) must have been enabled prior to the attack for you to get this information.</span></span>

## <a name="how-to-stop-and-remediate-an-illicit-consent-grant-attack"></a><span data-ttu-id="6f85e-176">方法不法な同意の付与攻撃を停止および修復する方法</span><span class="sxs-lookup"><span data-stu-id="6f85e-176">How to stop and remediate an illicit consent grant attack</span></span>

<span data-ttu-id="6f85e-177">不法なアクセス許可を使用してアプリケーションを識別した後、そのアクセスを削除する方法がいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="6f85e-177">After you have identified an application with illicit permissions, you have several ways to remove that access.</span></span>

- <span data-ttu-id="6f85e-178">Azure Active Directory ポータルのアプリケーションのアクセス許可は、次の方法で取り消すことができます。</span><span class="sxs-lookup"><span data-stu-id="6f85e-178">You can revoke the application's permission in the Azure Active Directory Portal by:</span></span>

  - <span data-ttu-id="6f85e-179">**Azure Active Directory ユーザー**ブレードの影響を受けるユーザーに移動します。</span><span class="sxs-lookup"><span data-stu-id="6f85e-179">Navigate to the affected user in the **Azure Active Directory User** blade.</span></span>

  - <span data-ttu-id="6f85e-180">[**アプリケーション**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6f85e-180">Select **Applications**.</span></span>

  - <span data-ttu-id="6f85e-181">違法アプリケーションを選択します。</span><span class="sxs-lookup"><span data-stu-id="6f85e-181">Select the illicit application.</span></span>

  - <span data-ttu-id="6f85e-182">ドリルダウンで [**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6f85e-182">Click **Remove** in the drill down.</span></span>

- <span data-ttu-id="6f85e-183">PowerShell で OAuth 同意の付与を取り消すには、 [AzureADOAuth2PermissionGrant](https://docs.microsoft.com/powershell/module/azuread/Remove-AzureADOAuth2PermissionGrant)の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="6f85e-183">You can revoke the OAuth consent grant with PowerShell by following the steps in [Remove-AzureADOAuth2PermissionGrant](https://docs.microsoft.com/powershell/module/azuread/Remove-AzureADOAuth2PermissionGrant).</span></span>

- <span data-ttu-id="6f85e-184">PowerShell を使用してサービスアプリの役割の割り当てを無効にするには、 [AzureADServiceAppRoleAssignment](https://docs.microsoft.com/powershell/module/azuread/Remove-AzureADServiceAppRoleAssignment)の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="6f85e-184">You can revoke the Service App Role Assignment with PowerShell by following the steps in [Remove-AzureADServiceAppRoleAssignment](https://docs.microsoft.com/powershell/module/azuread/Remove-AzureADServiceAppRoleAssignment).</span></span>

- <span data-ttu-id="6f85e-185">影響を受けるアカウントのサインインを完全に無効にすることもできます。これにより、そのアカウントのデータに対するアプリのアクセスが無効になります。</span><span class="sxs-lookup"><span data-stu-id="6f85e-185">You can also disable sign-in for the affected account altogether, which will in turn disable app access to data in that account.</span></span> <span data-ttu-id="6f85e-186">これは、エンドユーザーの生産性を向上させるのには理想的ではありませんが、影響をすばやく抑えるために作業する場合は、実用的な短期的な修復になります。</span><span class="sxs-lookup"><span data-stu-id="6f85e-186">This isn't ideal for the end user's productivity, of course, but if you are working to limit impact quickly, it can be a viable short-term remediation.</span></span>

- <span data-ttu-id="6f85e-187">テナントのために統合アプリケーションをオフにすることができます。</span><span class="sxs-lookup"><span data-stu-id="6f85e-187">You can turn integrated applications off for your tenancy.</span></span> <span data-ttu-id="6f85e-188">これは、エンドユーザーがテナント全体に同意を付与する機能を無効にする重大な手順です。</span><span class="sxs-lookup"><span data-stu-id="6f85e-188">This is a drastic step that disables the ability for end users to grant consent on a tenant-wide basis.</span></span> <span data-ttu-id="6f85e-189">これにより、ユーザーが悪意のあるアプリケーションへのアクセスを誤って許可するのを防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="6f85e-189">This prevents your users from inadvertently granting access to a malicious application.</span></span> <span data-ttu-id="6f85e-190">これは、ユーザーがサードパーティ製のアプリケーションを使用して生産性を向上させることがひどくないため、強くお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="6f85e-190">This isn't strongly recommended as it severely impairs your users' ability to be productive with third party applications.</span></span> <span data-ttu-id="6f85e-191">これを行うには、[統合アプリをオンまたはオフ](https://docs.microsoft.com/office365/admin/misc/integrated-apps)にする手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="6f85e-191">You can do this by following the steps in [Turning Integrated Apps on or off](https://docs.microsoft.com/office365/admin/misc/integrated-apps).</span></span>

## <a name="secure-office-365-like-a-cybersecurity-pro"></a><span data-ttu-id="6f85e-192">cybersecurity pro などの Office 365 の保護</span><span class="sxs-lookup"><span data-stu-id="6f85e-192">Secure Office 365 like a cybersecurity pro</span></span>

<span data-ttu-id="6f85e-193">Office 365 サブスクリプションには、データとユーザーを保護するために使用できる強力なセキュリティ機能セットが用意されています。</span><span class="sxs-lookup"><span data-stu-id="6f85e-193">Your Office 365 subscription comes with a powerful set of security capabilities that you can use to protect your data and your users.</span></span> <span data-ttu-id="6f85e-194">[Office 365 セキュリティ ロードマップ - 最初の 30 日間、90 日間、およびそれ以降の最優先事項](security-roadmap.md)を使用して、Office 365 テナントをセキュリティで保護するために Microsoft が推奨するベスト プラクティスを実装します。</span><span class="sxs-lookup"><span data-stu-id="6f85e-194">Use the [Office 365 security roadmap - Top priorities for the first 30 days, 90 days, and beyond](security-roadmap.md) to implement Microsoft recommended best practices for securing your Office 365 tenant.</span></span>

- <span data-ttu-id="6f85e-195">最初の30日間に実行するタスク。</span><span class="sxs-lookup"><span data-stu-id="6f85e-195">Tasks to accomplish in the first 30 days.</span></span> <span data-ttu-id="6f85e-196">これらはすぐに影響を受け、ユーザーにとって影響が小さくなります。</span><span class="sxs-lookup"><span data-stu-id="6f85e-196">These have immediate affect and are low-impact to your users.</span></span>

- <span data-ttu-id="6f85e-p121">最初の 90 日間で完了すべき作業。作業の計画と実装に少し時間がかかりますが、セキュリティ体制は大幅に向上します。</span><span class="sxs-lookup"><span data-stu-id="6f85e-p121">Tasks to accomplish in 90 days. These take a bit more time to plan and implement but greatly improve your security posture.</span></span>

- <span data-ttu-id="6f85e-p122">90 日以降。最初の 90 日間の作業で保護が強化されます。</span><span class="sxs-lookup"><span data-stu-id="6f85e-p122">Beyond 90 days. These enhancements build in your first 90 days work.</span></span>

## <a name="see-also"></a><span data-ttu-id="6f85e-201">関連項目:</span><span class="sxs-lookup"><span data-stu-id="6f85e-201">See also:</span></span>

- <span data-ttu-id="6f85e-202">[[自分のアプリケーション] リスト内の予期しないアプリケーション](https://docs.microsoft.com/azure/active-directory/application-access-unexpected-application)は、データにアクセスするための予期しないアプリケーションがあることを認識した後に、管理者がさまざまなアクションを実行できるようにします。</span><span class="sxs-lookup"><span data-stu-id="6f85e-202">[Unexpected application in my applications list](https://docs.microsoft.com/azure/active-directory/application-access-unexpected-application) walks administrators through various actions they may want to take after realizing there are unexpected applications with access to data.</span></span>

- <span data-ttu-id="6f85e-203">[アプリケーションを Azure Active Directory と統合](https://docs.microsoft.com/azure/active-directory/active-directory-apps-permissions-consent)することは、同意とアクセス許可の概要です。</span><span class="sxs-lookup"><span data-stu-id="6f85e-203">[Integrating applications with Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-apps-permissions-consent) is a high-level overview of consent and permissions.</span></span>

- <span data-ttu-id="6f85e-204">[アプリケーションの開発に関する問題](https://docs.microsoft.com/azure/active-directory/active-directory-application-dev-development-content-map)さまざまな同意に関する記事へのリンクを提供します。</span><span class="sxs-lookup"><span data-stu-id="6f85e-204">[Problems developing my application](https://docs.microsoft.com/azure/active-directory/active-directory-application-dev-development-content-map) provides links to various consent related articles.</span></span>

- <span data-ttu-id="6f85e-205">「 [Azure Active Directory のアプリケーションおよびサービスプリンシパルオブジェクト (AZURE AD)」で](https://docs.microsoft.com/azure/active-directory/develop/active-directory-application-objects)は、アプリケーションモデルにとって中核となるアプリケーションおよびサービスプリンシパルオブジェクトの概要を示します。</span><span class="sxs-lookup"><span data-stu-id="6f85e-205">[Application and service principal objects in Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/develop/active-directory-application-objects) provides an overview of the Application and Service principal objects that are core to the application model.</span></span>

- <span data-ttu-id="6f85e-206">アプリへの[アクセスを管理](https://docs.microsoft.com/azure/active-directory/active-directory-managing-access-to-apps)すると、管理者がアプリへのユーザーアクセスを管理するために必要な機能の概要が表示されます。</span><span class="sxs-lookup"><span data-stu-id="6f85e-206">[Manage access to apps](https://docs.microsoft.com/azure/active-directory/active-directory-managing-access-to-apps) is an overview of the capabilities that administrators have to manage user access to apps.</span></span>
