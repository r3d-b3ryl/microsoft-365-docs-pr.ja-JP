---
title: Microsoft Office 365 での不正な同意付与の検出と修復
f1.keywords:
- NOCSH
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
ms.openlocfilehash: 0ff16d01c3fe0f150e5a39cec574bc80aead9661
ms.sourcegitcommit: 4986032867b8664a215178b5e095cbda021f3450
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/12/2020
ms.locfileid: "41957152"
---
# <a name="detect-and-remediate-illicit-consent-grants-in-office-365"></a><span data-ttu-id="f181d-103">Microsoft Office 365 での不正な同意付与の検出と修復</span><span class="sxs-lookup"><span data-stu-id="f181d-103">Detect and Remediate Illicit Consent Grants in Office 365</span></span>

<span data-ttu-id="f181d-104">**概要** Office 365 で不法な同意を付与する攻撃を認識し、修復する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f181d-104">**Summary**  Learn how to recognize and remediate the illicit consent grants attack in Office 365.</span></span>

## <a name="what-is-the-illicit-consent-grant-attack-in-office-365"></a><span data-ttu-id="f181d-105">Office 365 における不正な同意の付与攻撃</span><span class="sxs-lookup"><span data-stu-id="f181d-105">What is the illicit consent grant attack in Office 365?</span></span>

<span data-ttu-id="f181d-106">違法同意付与攻撃では、攻撃者は、連絡先情報、電子メール、ドキュメントなどのデータへのアクセスを要求する Azure 登録済みアプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="f181d-106">In an illicit consent grant attack, the attacker creates an Azure-registered application that requests access to data such as contact information, email, or documents.</span></span> <span data-ttu-id="f181d-107">その後、攻撃者はエンドユーザーに対して、フィッシング攻撃によるデータへのアクセスを許可するように指示するか、または信頼された web サイトに不法なコードを挿入します。</span><span class="sxs-lookup"><span data-stu-id="f181d-107">The attacker then tricks an end user into granting that application consent to access their data either through a phishing attack, or by injecting illicit code into a trusted website.</span></span> <span data-ttu-id="f181d-108">不正なアプリケーションに同意した後は、組織のアカウントを使用しなくても、データへのアカウントレベルのアクセス権が付与されます。</span><span class="sxs-lookup"><span data-stu-id="f181d-108">After the illicit application has been granted consent, it has account-level access to data without the need for an organizational account.</span></span> <span data-ttu-id="f181d-109">違反アカウントのパスワードをリセットしたり、アカウントに多要素認証 (MFA) を必要としたりするなど、通常の修復手順は、この種の攻撃に対しては有効ではありません。これらはサードパーティのアプリケーションであり、組織の外部にあるためです。</span><span class="sxs-lookup"><span data-stu-id="f181d-109">Normal remediation steps, like resetting passwords for breached accounts or requiring Multi-Factor Authentication (MFA) on accounts, are not effective against this type of attack, since these are third-party applications and are external to the organization.</span></span> <span data-ttu-id="f181d-110">これらの攻撃は、情報を呼び出しているエンティティが人間ではなく、オートメーションであることを前提とする相互作用モデルを利用します。</span><span class="sxs-lookup"><span data-stu-id="f181d-110">These attacks leverage an interaction model which presumes the entity that is calling the information is automation and not a human.</span></span>

## <a name="what-does-an-illicit-consent-grant-attack-look-like-in-office-365"></a><span data-ttu-id="f181d-111">Office 365 のように、不法な同意を与える攻撃はどのようになりますか?</span><span class="sxs-lookup"><span data-stu-id="f181d-111">What does an illicit consent grant attack look like in Office 365?</span></span>

<span data-ttu-id="f181d-112">この攻撃の兆候 (IOC) を検出するには、Office 365**監査ログ**を検索する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f181d-112">You need to search the Office 365 **audit log** to find signs, also called Indicators of Compromise (IOC) of this attack.</span></span> <span data-ttu-id="f181d-113">Azure に登録されているアプリケーションの数が多く、ユーザーが大規模な組織では、組織の同意の付与を週単位で確認することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f181d-113">For organizations with many Azure-registered applications and a large user base, the best practice is to review your organizations consent grants on a weekly basis.</span></span>

### <a name="steps-for-finding-signs-of-this-attack"></a><span data-ttu-id="f181d-114">この攻撃の兆候を見つけるための手順</span><span class="sxs-lookup"><span data-stu-id="f181d-114">Steps for finding signs of this attack</span></span>

1. <span data-ttu-id="f181d-115">Office 365 テナントの [**セキュリティとコンプライアンスセンター** ] を開きます。</span><span class="sxs-lookup"><span data-stu-id="f181d-115">Open the **Security and Compliance Center** in your Office 365 tenant.</span></span>

2. <span data-ttu-id="f181d-116">[**検索**] に移動して、[**監査ログの検索**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f181d-116">Navigate to **Search** and select **Audit log search**.</span></span>

3. <span data-ttu-id="f181d-117">検索 (すべてのアクティビティとすべてのユーザー)、必要に応じて開始日と終了日を入力し、[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f181d-117">Search (all activities and all users) and enter the start date and end date if required and then click **Search**.</span></span> 

4. <span data-ttu-id="f181d-118">アプリケーションに対する同意のために結果をフィルター処理し、OAuth2PermissionGrant を追加します。</span><span class="sxs-lookup"><span data-stu-id="f181d-118">Filter the results for Consent to application, and Add OAuth2PermissionGrant.</span></span>

5. <span data-ttu-id="f181d-119">結果をクリックして、アクティビティの詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="f181d-119">Click on the result to see the details of the activity.</span></span> <span data-ttu-id="f181d-120">[**詳細情報**] をクリックして、アクティビティの詳細を取得します。</span><span class="sxs-lookup"><span data-stu-id="f181d-120">Click **More Information** to get details of the activity.</span></span> <span data-ttu-id="f181d-121">IsAdminContent が True に設定されているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="f181d-121">Check to see if IsAdminContent is set to True.</span></span>

> [!NOTE]
> <span data-ttu-id="f181d-122">•対応する監査ログエントリが検索結果に表示されるまでに、イベントが発生した後、最大30分または最大24時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="f181d-122">• It can take up to 30 minutes or up to 24 hours after an event occurs for the corresponding audit log entry to be displayed in the search results.</span></span> <br/><br/> <span data-ttu-id="f181d-123">•監査レコードが保持され、監査ログで検索可能になる時間の長さは、Office 365 のサブスクリプション、および特定のユーザーに割り当てられているライセンスの種類によって異なります。</span><span class="sxs-lookup"><span data-stu-id="f181d-123">• The length of time that an audit record is retained and searchable in the audit log depends on your Office 365 subscription, and specifically the type of the license that is assigned to a specific user.</span></span> <span data-ttu-id="f181d-124">詳細については、「[監査ログ](../../compliance/search-the-audit-log-in-security-and-compliance.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f181d-124">For more information, see [Audit log](../../compliance/search-the-audit-log-in-security-and-compliance.md).</span></span>
<span data-ttu-id="f181d-125">この値が true の場合は、グローバル管理者のアクセス権を持つユーザーがデータへの広範なアクセス権を持っている可能性があることを示します。</span><span class="sxs-lookup"><span data-stu-id="f181d-125">If this value is true, it indicates that someone with Global Administrator access may have granted broad access to data.</span></span> <span data-ttu-id="f181d-126">これが予期しない場合は、[攻撃を確認](#how-to-confirm-an-attack)するための手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="f181d-126">If this is unexpected, take steps to [confirm an attack](#how-to-confirm-an-attack).</span></span>

## <a name="how-to-confirm-an-attack"></a><span data-ttu-id="f181d-127">攻撃を確認する方法</span><span class="sxs-lookup"><span data-stu-id="f181d-127">How to confirm an attack</span></span>

<span data-ttu-id="f181d-128">上記の IOCs のインスタンスが1つ以上ある場合は、攻撃が発生したことを確認するためにさらに調査する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f181d-128">If you have one or more instances of the IOCs listed above, you need to do further investigation to positively confirm that the attack occurred.</span></span> <span data-ttu-id="f181d-129">これら3つの方法のいずれかを使用して、攻撃を確認できます。</span><span class="sxs-lookup"><span data-stu-id="f181d-129">You can use any of these three methods to confirm the attack.</span></span>

- <span data-ttu-id="f181d-130">Azure Active Directory ポータルを使用した、アプリケーションとそのアクセス許可の一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="f181d-130">Inventory applications and their permissions using the Azure Active Directory portal.</span></span> <span data-ttu-id="f181d-131">この方法は徹底していますが、チェックするユーザーが多い場合は、一度に1人のユーザーをチェックするだけで十分な時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="f181d-131">This method is thorough, but you can only check one user at a time which can be very time consuming if you have many users to check.</span></span>

- <span data-ttu-id="f181d-132">PowerShell を使用した、アプリケーションとそのアクセス許可の一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="f181d-132">Inventory applications and their permissions using PowerShell.</span></span> <span data-ttu-id="f181d-133">これは、最も少ないオーバーヘッドを最小限にした最も高速かつ最も綿密な方法です。</span><span class="sxs-lookup"><span data-stu-id="f181d-133">This is the fastest and most thorough method, with the least amount of overhead.</span></span>

- <span data-ttu-id="f181d-134">ユーザーが自分のアプリとアクセス許可を個別に確認して、修復のために管理者に結果を報告するようにします。</span><span class="sxs-lookup"><span data-stu-id="f181d-134">Have your users individually check their apps and permissions and report the results back to the administrators for remediation.</span></span>

## <a name="inventory-apps-with-access-in-your-organization"></a><span data-ttu-id="f181d-135">組織内でアクセスできるインベントリアプリ</span><span class="sxs-lookup"><span data-stu-id="f181d-135">Inventory apps with access in your organization</span></span>

<span data-ttu-id="f181d-136">これは、Azure Active Directory ポータルまたは PowerShell を使用しているユーザーに対して行うことができます。または、ユーザーがアプリケーションアクセスを個別に列挙する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f181d-136">You can do this for your users with either the Azure Active Directory Portal, or PowerShell or have your users individually enumerate their application access.</span></span>

### <a name="steps-for-using-the-azure-active-directory-portal"></a><span data-ttu-id="f181d-137">Azure Active Directory ポータルを使用するための手順</span><span class="sxs-lookup"><span data-stu-id="f181d-137">Steps for using the Azure Active Directory Portal</span></span>

<span data-ttu-id="f181d-138">[Azure Active Directory ポータル](https://portal.azure.com/)を使用して、個々のユーザーがアクセス許可を付与したアプリケーションを検索できます。</span><span class="sxs-lookup"><span data-stu-id="f181d-138">You can look up the applications to which any individual user has granted permissions by using the [Azure Active Directory Portal](https://portal.azure.com/).</span></span>

1. <span data-ttu-id="f181d-139">管理者権限を使用して Azure Portal にサインインします。</span><span class="sxs-lookup"><span data-stu-id="f181d-139">Sign in to the Azure Portal with administrative rights.</span></span>

2. <span data-ttu-id="f181d-140">Azure Active Directory ブレードを選択します。</span><span class="sxs-lookup"><span data-stu-id="f181d-140">Select the Azure Active Directory blade.</span></span>

3. <span data-ttu-id="f181d-141">[**ユーザー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f181d-141">Select **Users**.</span></span>

4. <span data-ttu-id="f181d-142">確認するユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="f181d-142">Select the user that you want to review.</span></span>

5. <span data-ttu-id="f181d-143">[**アプリケーション**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f181d-143">Select **Applications**.</span></span>

<span data-ttu-id="f181d-144">これにより、ユーザーに割り当てられているアプリと、applcations に設定されているアクセス許可が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f181d-144">This will show you the apps that are assigned to the user and what permissions the applcations have.</span></span>

### <a name="steps-for-having-your-users-enumerate-their-application-access"></a><span data-ttu-id="f181d-145">ユーザーがアプリケーションアクセスを列挙する手順</span><span class="sxs-lookup"><span data-stu-id="f181d-145">Steps for having your users enumerate their application access</span></span>

<span data-ttu-id="f181d-146">ユーザーが自分のアプリケーションhttps://myapps.microsoft.comへのアクセスを確認してもらいます。</span><span class="sxs-lookup"><span data-stu-id="f181d-146">Have your users go to https://myapps.microsoft.com and review their own application access there.</span></span> <span data-ttu-id="f181d-147">これらのユーザーは、アクセス可能なすべてのアプリを表示したり、それらに関する詳細を表示したり (アクセスの範囲を含む)、疑わしいまたは不法なアプリに対して権限を取り消すことができます。</span><span class="sxs-lookup"><span data-stu-id="f181d-147">They should be able to see all the apps with access, view details about them (including the scope of access), and be able to revoke privileges to suspicious or illicit apps.</span></span>

### <a name="steps-for-doing-this-with-powershell"></a><span data-ttu-id="f181d-148">PowerShell を使用してこれを行うための手順</span><span class="sxs-lookup"><span data-stu-id="f181d-148">Steps for doing this with PowerShell</span></span>

<span data-ttu-id="f181d-149">不法同意付与攻撃を確認する最も簡単な方法は、 [Get-AzureADPSPermissions](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09)を実行することです。これにより、テナント内のすべてのユーザーの oauth 承諾許可と oauth アプリがすべて、1つの .csv ファイルにダンプされます。</span><span class="sxs-lookup"><span data-stu-id="f181d-149">The simplest way to verify the Illicit Consent Grant attack is to run [Get-AzureADPSPermissions.ps1](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09), which will dump all the OAuth consent grants and OAuth apps for all users in your tenancy into one .csv file.</span></span>

#### <a name="pre-requisites"></a><span data-ttu-id="f181d-150">前提条件</span><span class="sxs-lookup"><span data-stu-id="f181d-150">Pre-requisites</span></span>

- <span data-ttu-id="f181d-151">Azure AD PowerShell ライブラリがインストールされていること。</span><span class="sxs-lookup"><span data-stu-id="f181d-151">The Azure AD PowerShell library installed.</span></span>

- <span data-ttu-id="f181d-152">スクリプトが実行されるテナントのグローバル管理者権限。</span><span class="sxs-lookup"><span data-stu-id="f181d-152">Global administrator rights on the tenant that the script will be run against.</span></span>

- <span data-ttu-id="f181d-153">スクリプトを実行するコンピューターのローカル管理者。</span><span class="sxs-lookup"><span data-stu-id="f181d-153">Local Administrator on the computer from which will run the scripts.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f181d-154">管理アカウントでは、多要素認証を必要とすることを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f181d-154">We highly recommend that you require multi-factor authentication on your administrative account.</span></span> <span data-ttu-id="f181d-155">このスクリプトは、MFA 認証をサポートします。</span><span class="sxs-lookup"><span data-stu-id="f181d-155">This script supports MFA authentication.</span></span>

1. <span data-ttu-id="f181d-156">スクリプトを実行するコンピューターに、ローカル管理者権限を使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="f181d-156">Sign in to the computer that you will run the script from with local administrator rights.</span></span>

2. <span data-ttu-id="f181d-157">GitHub から scruipt を実行するフォルダーに[Get-AzureADPSPermissions](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09)スクリプトをダウンロードするか、コピーします。</span><span class="sxs-lookup"><span data-stu-id="f181d-157">Download or copy the [Get-AzureADPSPermissions.ps1](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09) script from GitHub to a folder from which you will run the scruipt.</span></span> <span data-ttu-id="f181d-158">これは、出力 "permissions" ファイルが書き込まれるフォルダーと同じです。</span><span class="sxs-lookup"><span data-stu-id="f181d-158">This will be the same folder to which the output "permissions.csv" file will be written.</span></span>

3. <span data-ttu-id="f181d-159">管理者として PowerShell インスタンスを開き、スクリプトを保存したフォルダーを開きます。</span><span class="sxs-lookup"><span data-stu-id="f181d-159">Open a PowerShell instance as an administrator and open to the folder you saved the script to.</span></span>

4. <span data-ttu-id="f181d-160">[AzureAD](https://docs.microsoft.com/powershell/module/azuread/connect-azuread)コマンドレットを使用して、ディレクトリに接続します。</span><span class="sxs-lookup"><span data-stu-id="f181d-160">Connect to your directory using the [Connect-AzureAD](https://docs.microsoft.com/powershell/module/azuread/connect-azuread) cmdlet.</span></span>

5. <span data-ttu-id="f181d-161">次の PowerShell コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="f181d-161">Run this PowerShell command:</span></span>

   ```powershell
   Get-AzureADPSPermissions.ps1 | Export-csv -Path "Permissions.csv" -NoTypeInformation
   ```

<span data-ttu-id="f181d-162">スクリプトによって、Permissions という名前のファイルが1つ作成されます。</span><span class="sxs-lookup"><span data-stu-id="f181d-162">The script produces one file named Permissions.csv.</span></span> <span data-ttu-id="f181d-163">次の手順に従って、不法なアプリケーションアクセス許可の付与を検索します。</span><span class="sxs-lookup"><span data-stu-id="f181d-163">Follow these steps to look for illicit application permission grants:</span></span>

1. <span data-ttu-id="f181d-164">[Conな種類] 列 (列 G) で、値 "AllPrinciples" を検索します。</span><span class="sxs-lookup"><span data-stu-id="f181d-164">In the ConsentType column (column G) search for the value "AllPrinciples".</span></span> <span data-ttu-id="f181d-165">AllPrincipals アクセス許可によって、クライアントアプリケーションは、テナント内のすべてのユーザーのコンテンツにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="f181d-165">The AllPrincipals permission allows the client application to access everyone's content in the tenancy.</span></span> <span data-ttu-id="f181d-166">ネイティブの Office 365 アプリケーションは、正しく動作するためにこのアクセス許可を必要とします。</span><span class="sxs-lookup"><span data-stu-id="f181d-166">Native Office 365 applications need this permission to work correctly.</span></span> <span data-ttu-id="f181d-167">このアクセス許可を持つ Microsoft 以外のすべてのアプリケーションは、慎重にレビューする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f181d-167">Every non-Microsoft application with this permission should be reviewed carefully.</span></span>

2. <span data-ttu-id="f181d-168">[アクセス許可] 列 (列 F) に、各委任されたアプリケーションがコンテンツに対して持っているアクセス許可を確認します。</span><span class="sxs-lookup"><span data-stu-id="f181d-168">In the Permission column (column F) review the permissions that each delegated application has to content.</span></span> <span data-ttu-id="f181d-169">"読み取り" と "書き込み" アクセス許可または "\* を探します。All "アクセス許可を使用して、適切ではない可能性があるため慎重に確認してください。</span><span class="sxs-lookup"><span data-stu-id="f181d-169">Look for "Read" and "Write" permission or "\*.All" permission, and review these carefully because they may not be appropriate.</span></span>

3. <span data-ttu-id="f181d-170">同意が付与されている特定のユーザーを確認します。</span><span class="sxs-lookup"><span data-stu-id="f181d-170">Review the specific users that have consents granted.</span></span> <span data-ttu-id="f181d-171">プロファイルが大きい場合や、影響度の高いユーザーに不適切な同意が付与されている場合は、さらに詳しく調査する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f181d-171">If high profile or high impact users have inappropriate consents granted, you should investigate further.</span></span>

4. <span data-ttu-id="f181d-172">[ClientDisplayName] 列 (列 C) で、疑わしいと思われるアプリを探します。</span><span class="sxs-lookup"><span data-stu-id="f181d-172">In the ClientDisplayName column (column C) look for apps that seem suspicious.</span></span> <span data-ttu-id="f181d-173">名前のスペルが間違っているアプリ、super bland names、またはハッカーが発音した名前は、慎重に検討する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f181d-173">Apps with misspelled names, super bland names, or hacker-sounding names should be reviewed carefully.</span></span>

## <a name="determine-the-scope-of-the-attack"></a><span data-ttu-id="f181d-174">攻撃の範囲を決定する</span><span class="sxs-lookup"><span data-stu-id="f181d-174">Determine the scope of the attack</span></span>

<span data-ttu-id="f181d-175">アプリケーションアクセスのインベントリ処理が終了したら、Office 365**監査ログ**を確認して、違反の完全なスコープを特定します。</span><span class="sxs-lookup"><span data-stu-id="f181d-175">After you have finished inventorying application access, review the Office 365 **audit log** to determine the full scope of the breach.</span></span> <span data-ttu-id="f181d-176">影響を受けるユーザー、不法アプリケーションが組織にアクセスした時間枠、およびアプリのアクセス許可を検索します。</span><span class="sxs-lookup"><span data-stu-id="f181d-176">Search on the affected users, the time frames that the illicit application had access to your organization, and the permissions the app had.</span></span> <span data-ttu-id="f181d-177">**監査ログ**は、 [Microsoft 365 セキュリティ/コンプライアンスセンター](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)で検索できます。</span><span class="sxs-lookup"><span data-stu-id="f181d-177">You can search the **audit log** in the [Microsoft 365 Security and Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f181d-178">この情報を取得するには、攻撃の前に、[管理者とユーザーの](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off)[メールボックスの監査](https://docs.microsoft.com/microsoft-365/compliance/enable-mailbox-auditing)とアクティビティの監査を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f181d-178">[Mailbox auditing](https://docs.microsoft.com/microsoft-365/compliance/enable-mailbox-auditing) and [Activity auditing for admins and users](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off) must have been enabled prior to the attack for you to get this information.</span></span>

## <a name="how-to-stop-and-remediate-an-illicit-consent-grant-attack"></a><span data-ttu-id="f181d-179">方法不法な同意の付与攻撃を停止および修復する方法</span><span class="sxs-lookup"><span data-stu-id="f181d-179">How to stop and remediate an illicit consent grant attack</span></span>

<span data-ttu-id="f181d-180">不法なアクセス許可を使用してアプリケーションを識別した後、そのアクセスを削除する方法がいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="f181d-180">After you have identified an application with illicit permissions, you have several ways to remove that access.</span></span>

- <span data-ttu-id="f181d-181">Azure Active Directory ポータルのアプリケーションのアクセス許可は、次の方法で取り消すことができます。</span><span class="sxs-lookup"><span data-stu-id="f181d-181">You can revoke the application's permission in the Azure Active Directory Portal by:</span></span>

  - <span data-ttu-id="f181d-182">**Azure Active Directory ユーザー**ブレードの影響を受けるユーザーに移動します。</span><span class="sxs-lookup"><span data-stu-id="f181d-182">Navigate to the affected user in the **Azure Active Directory User** blade.</span></span>

  - <span data-ttu-id="f181d-183">[**アプリケーション**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f181d-183">Select **Applications**.</span></span>

  - <span data-ttu-id="f181d-184">違法アプリケーションを選択します。</span><span class="sxs-lookup"><span data-stu-id="f181d-184">Select the illicit application.</span></span>

  - <span data-ttu-id="f181d-185">ドリルダウンで [**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f181d-185">Click **Remove** in the drill down.</span></span>

- <span data-ttu-id="f181d-186">PowerShell で OAuth 同意の付与を取り消すには、 [AzureADOAuth2PermissionGrant](https://docs.microsoft.com/powershell/module/azuread/Remove-AzureADOAuth2PermissionGrant)の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="f181d-186">You can revoke the OAuth consent grant with PowerShell by following the steps in [Remove-AzureADOAuth2PermissionGrant](https://docs.microsoft.com/powershell/module/azuread/Remove-AzureADOAuth2PermissionGrant).</span></span>

- <span data-ttu-id="f181d-187">PowerShell を使用してサービスアプリの役割の割り当てを無効にするには、 [AzureADServiceAppRoleAssignment](https://docs.microsoft.com/powershell/module/azuread/Remove-AzureADServiceAppRoleAssignment)の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="f181d-187">You can revoke the Service App Role Assignment with PowerShell by following the steps in [Remove-AzureADServiceAppRoleAssignment](https://docs.microsoft.com/powershell/module/azuread/Remove-AzureADServiceAppRoleAssignment).</span></span>

- <span data-ttu-id="f181d-188">影響を受けるアカウントのサインインを完全に無効にすることもできます。これにより、そのアカウントのデータに対するアプリのアクセスが無効になります。</span><span class="sxs-lookup"><span data-stu-id="f181d-188">You can also disable sign-in for the affected account altogether, which will in turn disable app access to data in that account.</span></span> <span data-ttu-id="f181d-189">これは、エンドユーザーの生産性を向上させるのには理想的ではありませんが、影響をすばやく抑えるために作業する場合は、実用的な短期的な修復になります。</span><span class="sxs-lookup"><span data-stu-id="f181d-189">This isn't ideal for the end user's productivity, of course, but if you are working to limit impact quickly, it can be a viable short-term remediation.</span></span>

- <span data-ttu-id="f181d-190">テナントのために統合アプリケーションをオフにすることができます。</span><span class="sxs-lookup"><span data-stu-id="f181d-190">You can turn integrated applications off for your tenancy.</span></span> <span data-ttu-id="f181d-191">これは、エンドユーザーがテナント全体に同意を付与する機能を無効にする重大な手順です。</span><span class="sxs-lookup"><span data-stu-id="f181d-191">This is a drastic step that disables the ability for end users to grant consent on a tenant-wide basis.</span></span> <span data-ttu-id="f181d-192">これにより、ユーザーが悪意のあるアプリケーションへのアクセスを誤って許可するのを防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="f181d-192">This prevents your users from inadvertently granting access to a malicious application.</span></span> <span data-ttu-id="f181d-193">これは、ユーザーがサードパーティ製のアプリケーションを使用して生産性を向上させることがひどくないため、強くお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="f181d-193">This isn't strongly recommended as it severely impairs your users' ability to be productive with third party applications.</span></span> <span data-ttu-id="f181d-194">これを行うには、[統合アプリをオンまたはオフ](https://docs.microsoft.com/office365/admin/misc/integrated-apps)にする手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="f181d-194">You can do this by following the steps in [Turning Integrated Apps on or off](https://docs.microsoft.com/office365/admin/misc/integrated-apps).</span></span>

## <a name="secure-office-365-like-a-cybersecurity-pro"></a><span data-ttu-id="f181d-195">cybersecurity pro などの Office 365 の保護</span><span class="sxs-lookup"><span data-stu-id="f181d-195">Secure Office 365 like a cybersecurity pro</span></span>

<span data-ttu-id="f181d-196">Office 365 サブスクリプションには、データとユーザーを保護するために使用できる強力なセキュリティ機能セットが用意されています。</span><span class="sxs-lookup"><span data-stu-id="f181d-196">Your Office 365 subscription comes with a powerful set of security capabilities that you can use to protect your data and your users.</span></span> <span data-ttu-id="f181d-197">[Office 365 セキュリティ ロードマップ - 最初の 30 日間、90 日間、およびそれ以降の最優先事項](security-roadmap.md)を使用して、Office 365 テナントをセキュリティで保護するために Microsoft が推奨するベスト プラクティスを実装します。</span><span class="sxs-lookup"><span data-stu-id="f181d-197">Use the [Office 365 security roadmap - Top priorities for the first 30 days, 90 days, and beyond](security-roadmap.md) to implement Microsoft recommended best practices for securing your Office 365 tenant.</span></span>

- <span data-ttu-id="f181d-198">最初の30日間に実行するタスク。</span><span class="sxs-lookup"><span data-stu-id="f181d-198">Tasks to accomplish in the first 30 days.</span></span> <span data-ttu-id="f181d-199">これらはすぐに影響を受け、ユーザーにとって影響が小さくなります。</span><span class="sxs-lookup"><span data-stu-id="f181d-199">These have immediate affect and are low-impact to your users.</span></span>

- <span data-ttu-id="f181d-p122">最初の 90 日間で完了すべき作業。作業の計画と実装に少し時間がかかりますが、セキュリティ体制は大幅に向上します。</span><span class="sxs-lookup"><span data-stu-id="f181d-p122">Tasks to accomplish in 90 days. These take a bit more time to plan and implement but greatly improve your security posture.</span></span>

- <span data-ttu-id="f181d-p123">90 日以降。最初の 90 日間の作業で保護が強化されます。</span><span class="sxs-lookup"><span data-stu-id="f181d-p123">Beyond 90 days. These enhancements build in your first 90 days work.</span></span>

## <a name="see-also"></a><span data-ttu-id="f181d-204">関連項目:</span><span class="sxs-lookup"><span data-stu-id="f181d-204">See also:</span></span>

- <span data-ttu-id="f181d-205">[[自分のアプリケーション] リスト内の予期しないアプリケーション](https://docs.microsoft.com/azure/active-directory/application-access-unexpected-application)は、データにアクセスするための予期しないアプリケーションがあることを認識した後に、管理者がさまざまなアクションを実行できるようにします。</span><span class="sxs-lookup"><span data-stu-id="f181d-205">[Unexpected application in my applications list](https://docs.microsoft.com/azure/active-directory/application-access-unexpected-application) walks administrators through various actions they may want to take after realizing there are unexpected applications with access to data.</span></span>

- <span data-ttu-id="f181d-206">[アプリケーションを Azure Active Directory と統合](https://docs.microsoft.com/azure/active-directory/active-directory-apps-permissions-consent)することは、同意とアクセス許可の概要です。</span><span class="sxs-lookup"><span data-stu-id="f181d-206">[Integrating applications with Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-apps-permissions-consent) is a high-level overview of consent and permissions.</span></span>

- <span data-ttu-id="f181d-207">[アプリケーションの開発に関する問題](https://docs.microsoft.com/azure/active-directory/active-directory-application-dev-development-content-map)さまざまな同意に関する記事へのリンクを提供します。</span><span class="sxs-lookup"><span data-stu-id="f181d-207">[Problems developing my application](https://docs.microsoft.com/azure/active-directory/active-directory-application-dev-development-content-map) provides links to various consent related articles.</span></span>

- <span data-ttu-id="f181d-208">「 [Azure Active Directory のアプリケーションおよびサービスプリンシパルオブジェクト (AZURE AD)」で](https://docs.microsoft.com/azure/active-directory/develop/active-directory-application-objects)は、アプリケーションモデルにとって中核となるアプリケーションおよびサービスプリンシパルオブジェクトの概要を示します。</span><span class="sxs-lookup"><span data-stu-id="f181d-208">[Application and service principal objects in Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/develop/active-directory-application-objects) provides an overview of the Application and Service principal objects that are core to the application model.</span></span>

- <span data-ttu-id="f181d-209">アプリへの[アクセスを管理](https://docs.microsoft.com/azure/active-directory/active-directory-managing-access-to-apps)すると、管理者がアプリへのユーザーアクセスを管理するために必要な機能の概要が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f181d-209">[Manage access to apps](https://docs.microsoft.com/azure/active-directory/active-directory-managing-access-to-apps) is an overview of the capabilities that administrators have to manage user access to apps.</span></span>
