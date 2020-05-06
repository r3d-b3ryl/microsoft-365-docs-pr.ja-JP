---
title: 不法な同意の付与を検出して修復する
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
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
description: Microsoft Office 365 で不法な同意を与える攻撃を認識して修復する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c7ba6c521c814e4ea44c2dc29ccdad8143d166d4
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034830"
---
# <a name="detect-and-remediate-illicit-consent-grants"></a><span data-ttu-id="b2120-103">不法な同意の付与を検出して修復する</span><span class="sxs-lookup"><span data-stu-id="b2120-103">Detect and Remediate Illicit Consent Grants</span></span>

<span data-ttu-id="b2120-104">**概要** Office 365 で不法な同意を付与する攻撃を認識し、修復する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b2120-104">**Summary**  Learn how to recognize and remediate the illicit consent grants attack in Office 365.</span></span>

## <a name="what-is-the-illicit-consent-grant-attack-in-office-365"></a><span data-ttu-id="b2120-105">Office 365 における不正な同意の付与攻撃</span><span class="sxs-lookup"><span data-stu-id="b2120-105">What is the illicit consent grant attack in Office 365?</span></span>

<span data-ttu-id="b2120-106">違法同意付与攻撃では、攻撃者は、連絡先情報、電子メール、ドキュメントなどのデータへのアクセスを要求する Azure 登録済みアプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="b2120-106">In an illicit consent grant attack, the attacker creates an Azure-registered application that requests access to data such as contact information, email, or documents.</span></span> <span data-ttu-id="b2120-107">その後、攻撃者はエンドユーザーに対して、フィッシング攻撃によるデータへのアクセスを許可するように指示するか、または信頼された web サイトに不法なコードを挿入します。</span><span class="sxs-lookup"><span data-stu-id="b2120-107">The attacker then tricks an end user into granting that application consent to access their data either through a phishing attack, or by injecting illicit code into a trusted website.</span></span> <span data-ttu-id="b2120-108">不正なアプリケーションに同意した後は、組織のアカウントを使用しなくても、データへのアカウントレベルのアクセス権が付与されます。</span><span class="sxs-lookup"><span data-stu-id="b2120-108">After the illicit application has been granted consent, it has account-level access to data without the need for an organizational account.</span></span> <span data-ttu-id="b2120-109">違反アカウントのパスワードをリセットしたり、アカウントに多要素認証 (MFA) を必要としたりするなど、通常の修復手順は、この種の攻撃に対しては有効ではありません。これらはサードパーティのアプリケーションであり、組織の外部にあるためです。</span><span class="sxs-lookup"><span data-stu-id="b2120-109">Normal remediation steps, like resetting passwords for breached accounts or requiring Multi-Factor Authentication (MFA) on accounts, are not effective against this type of attack, since these are third-party applications and are external to the organization.</span></span> 

<span data-ttu-id="b2120-110">これらの攻撃は、情報を呼び出しているエンティティが人間ではなく、オートメーションであることを前提とする相互作用モデルを利用します。</span><span class="sxs-lookup"><span data-stu-id="b2120-110">These attacks leverage an interaction model which presumes the entity that is calling the information is automation and not a human.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b2120-111">現時点では、アプリからの不法な同意を得られる問題が発生していると思われますか。</span><span class="sxs-lookup"><span data-stu-id="b2120-111">Do you suspect you're experiencing problems with illicit consent-grants from an app, right now?</span></span> <span data-ttu-id="b2120-112">Microsoft Cloud App Security (MCAS) には、OAuth アプリを検出、調査、修復するためのツールがあります。</span><span class="sxs-lookup"><span data-stu-id="b2120-112">Microsoft Cloud App Security (MCAS) has tools to detect, investigate, and remediate your OAuth apps.</span></span> <span data-ttu-id="b2120-113">この MCAS の記事には、[危険な OAuth アプリを調査](https://docs.microsoft.com/cloud-app-security/investigate-risky-oauth)する方法の概要を示すチュートリアルがあります。</span><span class="sxs-lookup"><span data-stu-id="b2120-113">This MCAS article has a tutorial that outlines how to go about [investigating risky OAuth apps](https://docs.microsoft.com/cloud-app-security/investigate-risky-oauth).</span></span> <span data-ttu-id="b2120-114">また、 [OAuth アプリポリシー](https://docs.microsoft.com/cloud-app-security/app-permission-policy)を設定して、アプリが要求するアクセス許可を調査し、ユーザーがこれらのアプリを承認して、これらのアクセス許可要求を幅広く承認または禁止することもできます。</span><span class="sxs-lookup"><span data-stu-id="b2120-114">You can also set [OAuth app policies](https://docs.microsoft.com/cloud-app-security/app-permission-policy) to investigate app-requested permissions, which users are authorizing these apps, and widely approve or ban these permissions requests.</span></span>

## <a name="what-does-an-illicit-consent-grant-attack-look-like-in-office-365"></a><span data-ttu-id="b2120-115">Office 365 のように、不法な同意を与える攻撃はどのようになりますか?</span><span class="sxs-lookup"><span data-stu-id="b2120-115">What does an illicit consent grant attack look like in Office 365?</span></span>

<span data-ttu-id="b2120-116">**監査ログ**を検索して、この攻撃の兆候の兆候 (IOC) と呼ばれることもあります。</span><span class="sxs-lookup"><span data-stu-id="b2120-116">You need to search the **audit log** to find signs, also called Indicators of Compromise (IOC) of this attack.</span></span> <span data-ttu-id="b2120-117">Azure に登録されているアプリケーションの数が多く、ユーザーが大規模な組織では、組織の同意の付与を週単位で確認することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b2120-117">For organizations with many Azure-registered applications and a large user base, the best practice is to review your organizations consent grants on a weekly basis.</span></span>

### <a name="steps-for-finding-signs-of-this-attack"></a><span data-ttu-id="b2120-118">この攻撃の兆候を見つけるための手順</span><span class="sxs-lookup"><span data-stu-id="b2120-118">Steps for finding signs of this attack</span></span>

1. <span data-ttu-id="b2120-119">テナント内の [**セキュリティ & コンプライアンスセンター** ] を開きます。</span><span class="sxs-lookup"><span data-stu-id="b2120-119">Open the **Security & Compliance Center** in your tenant.</span></span>

2. <span data-ttu-id="b2120-120">[**検索**] に移動して、[**監査ログの検索**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b2120-120">Navigate to **Search** and select **Audit log search**.</span></span>

3. <span data-ttu-id="b2120-121">検索 (すべてのアクティビティとすべてのユーザー)、必要に応じて開始日と終了日を入力し、[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b2120-121">Search (all activities and all users) and enter the start date and end date if required and then click **Search**.</span></span> 

4. <span data-ttu-id="b2120-122">[**結果のフィルター** ] をクリックし、[**アクティビティ**] フィールドに「アプリケーションへの同意」と入力します。</span><span class="sxs-lookup"><span data-stu-id="b2120-122">Click **Filter results** and enter Consent to application in the **Activity** field.</span></span>

5. <span data-ttu-id="b2120-123">結果をクリックして、アクティビティの詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="b2120-123">Click on the result to see the details of the activity.</span></span> <span data-ttu-id="b2120-124">[**詳細情報**] をクリックして、アクティビティの詳細を取得します。</span><span class="sxs-lookup"><span data-stu-id="b2120-124">Click **More Information** to get details of the activity.</span></span> <span data-ttu-id="b2120-125">IsAdminContent が True に設定されているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="b2120-125">Check to see if IsAdminContent is set to True.</span></span>

> [!NOTE]
> <span data-ttu-id="b2120-126">イベントが発生した後に、対応する監査ログエントリが検索結果に表示されるようにするには、30分から最大24時間かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="b2120-126">It can take from 30 minutes up to 24 hours for the corresponding audit log entry to be displayed in the search results after an event occurs.</span></span> <br/><br/> <span data-ttu-id="b2120-127">監査レコードが保持され、監査ログで検索可能な期間は、Microsoft 365 サブスクリプションによって異なり、具体的には特定のユーザーに割り当てられているライセンスの種類によって異なります。</span><span class="sxs-lookup"><span data-stu-id="b2120-127">The length of time that an audit record is retained and searchable in the audit log depends on your Microsoft 365 subscription, and specifically the type of the license that is assigned to a specific user.</span></span> <span data-ttu-id="b2120-128">詳細については、「[監査ログ](../../compliance/search-the-audit-log-in-security-and-compliance.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b2120-128">For more information, see [Audit log](../../compliance/search-the-audit-log-in-security-and-compliance.md).</span></span>
> 
> <span data-ttu-id="b2120-129">この値が true の場合は、グローバル管理者のアクセス権を持つユーザーがデータへの広範なアクセス権を持っている可能性があることを示します。</span><span class="sxs-lookup"><span data-stu-id="b2120-129">If this value is true, it indicates that someone with Global Administrator access may have granted broad access to data.</span></span> <span data-ttu-id="b2120-130">これが予期しない場合は、[攻撃を確認](#how-to-confirm-an-attack)するための手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="b2120-130">If this is unexpected, take steps to [confirm an attack](#how-to-confirm-an-attack).</span></span>

## <a name="how-to-confirm-an-attack"></a><span data-ttu-id="b2120-131">攻撃を確認する方法</span><span class="sxs-lookup"><span data-stu-id="b2120-131">How to confirm an attack</span></span>

<span data-ttu-id="b2120-132">上記の IOCs のインスタンスが1つ以上ある場合は、攻撃が発生したことを確認するためにさらに調査する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b2120-132">If you have one or more instances of the IOCs listed above, you need to do further investigation to positively confirm that the attack occurred.</span></span> <span data-ttu-id="b2120-133">次の3つの方法のいずれかを使用して、攻撃を確認できます。</span><span class="sxs-lookup"><span data-stu-id="b2120-133">You can use any of these three methods to confirm the attack:</span></span>

- <span data-ttu-id="b2120-134">Azure Active Directory ポータルを使用した、アプリケーションとそのアクセス許可の一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="b2120-134">Inventory applications and their permissions using the Azure Active Directory portal.</span></span> <span data-ttu-id="b2120-135">この方法は徹底していますが、チェックするユーザーが多い場合は、一度に1人のユーザーをチェックするだけで十分な時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="b2120-135">This method is thorough, but you can only check one user at a time which can be very time consuming if you have many users to check.</span></span>

- <span data-ttu-id="b2120-136">PowerShell を使用した、アプリケーションとそのアクセス許可の一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="b2120-136">Inventory applications and their permissions using PowerShell.</span></span> <span data-ttu-id="b2120-137">これは、最も少ないオーバーヘッドを最小限にした最も高速かつ最も綿密な方法です。</span><span class="sxs-lookup"><span data-stu-id="b2120-137">This is the fastest and most thorough method, with the least amount of overhead.</span></span>

- <span data-ttu-id="b2120-138">ユーザーが自分のアプリとアクセス許可を個別に確認して、修復のために管理者に結果を報告するようにします。</span><span class="sxs-lookup"><span data-stu-id="b2120-138">Have your users individually check their apps and permissions and report the results back to the administrators for remediation.</span></span>

## <a name="inventory-apps-with-access-in-your-organization"></a><span data-ttu-id="b2120-139">組織内でアクセスできるインベントリアプリ</span><span class="sxs-lookup"><span data-stu-id="b2120-139">Inventory apps with access in your organization</span></span>

<span data-ttu-id="b2120-140">これは、Azure Active Directory ポータルまたは PowerShell を使用しているユーザーに対して行うことができます。または、ユーザーがアプリケーションアクセスを個別に列挙する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b2120-140">You can do this for your users with either the Azure Active Directory Portal, or PowerShell or have your users individually enumerate their application access.</span></span>

### <a name="steps-for-using-the-azure-active-directory-portal"></a><span data-ttu-id="b2120-141">Azure Active Directory ポータルを使用するための手順</span><span class="sxs-lookup"><span data-stu-id="b2120-141">Steps for using the Azure Active Directory Portal</span></span>

<span data-ttu-id="b2120-142">[Azure Active Directory ポータル](https://portal.azure.com/)を使用して、個々のユーザーがアクセス許可を付与したアプリケーションを検索できます。</span><span class="sxs-lookup"><span data-stu-id="b2120-142">You can look up the applications to which any individual user has granted permissions by using the [Azure Active Directory Portal](https://portal.azure.com/).</span></span>

1. <span data-ttu-id="b2120-143">管理者権限を使用して Azure Portal にサインインします。</span><span class="sxs-lookup"><span data-stu-id="b2120-143">Sign in to the Azure Portal with administrative rights.</span></span>

2. <span data-ttu-id="b2120-144">Azure Active Directory ブレードを選択します。</span><span class="sxs-lookup"><span data-stu-id="b2120-144">Select the Azure Active Directory blade.</span></span>

3. <span data-ttu-id="b2120-145">[**ユーザー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b2120-145">Select **Users**.</span></span>

4. <span data-ttu-id="b2120-146">確認するユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="b2120-146">Select the user that you want to review.</span></span>

5. <span data-ttu-id="b2120-147">[**アプリケーション**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b2120-147">Select **Applications**.</span></span>

<span data-ttu-id="b2120-148">これにより、ユーザーに割り当てられているアプリと、アプリケーションのアクセス許可が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b2120-148">This will show you the apps that are assigned to the user and what permissions the applications have.</span></span>

### <a name="steps-for-having-your-users-enumerate-their-application-access"></a><span data-ttu-id="b2120-149">ユーザーがアプリケーションアクセスを列挙する手順</span><span class="sxs-lookup"><span data-stu-id="b2120-149">Steps for having your users enumerate their application access</span></span>

<span data-ttu-id="b2120-150">ユーザーが自分のアプリケーションhttps://myapps.microsoft.comへのアクセスを確認してもらいます。</span><span class="sxs-lookup"><span data-stu-id="b2120-150">Have your users go to https://myapps.microsoft.com and review their own application access there.</span></span> <span data-ttu-id="b2120-151">これらのユーザーは、アクセス可能なすべてのアプリを表示したり、それらに関する詳細を表示したり (アクセスの範囲を含む)、疑わしいまたは不法なアプリに対して権限を取り消すことができます。</span><span class="sxs-lookup"><span data-stu-id="b2120-151">They should be able to see all the apps with access, view details about them (including the scope of access), and be able to revoke privileges to suspicious or illicit apps.</span></span>

### <a name="steps-for-doing-this-with-powershell"></a><span data-ttu-id="b2120-152">PowerShell を使用してこれを行うための手順</span><span class="sxs-lookup"><span data-stu-id="b2120-152">Steps for doing this with PowerShell</span></span>

<span data-ttu-id="b2120-153">不法同意付与攻撃を確認する最も簡単な方法は、 [Get-AzureADPSPermissions](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09)を実行することです。これにより、テナント内のすべてのユーザーの oauth 承諾許可と oauth アプリがすべて、1つの .csv ファイルにダンプされます。</span><span class="sxs-lookup"><span data-stu-id="b2120-153">The simplest way to verify the Illicit Consent Grant attack is to run [Get-AzureADPSPermissions.ps1](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09), which will dump all the OAuth consent grants and OAuth apps for all users in your tenancy into one .csv file.</span></span>

#### <a name="pre-requisites"></a><span data-ttu-id="b2120-154">前提条件</span><span class="sxs-lookup"><span data-stu-id="b2120-154">Pre-requisites</span></span>

- <span data-ttu-id="b2120-155">Azure AD PowerShell ライブラリがインストールされていること。</span><span class="sxs-lookup"><span data-stu-id="b2120-155">The Azure AD PowerShell library installed.</span></span>

- <span data-ttu-id="b2120-156">スクリプトが実行されるテナントのグローバル管理者権限。</span><span class="sxs-lookup"><span data-stu-id="b2120-156">Global administrator rights on the tenant that the script will be run against.</span></span>

- <span data-ttu-id="b2120-157">スクリプトを実行するコンピューターのローカル管理者。</span><span class="sxs-lookup"><span data-stu-id="b2120-157">Local Administrator on the computer from which will run the scripts.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b2120-158">管理アカウントでは、多要素認証を必要とすることを***強くお勧め***します。</span><span class="sxs-lookup"><span data-stu-id="b2120-158">We ***highly recommend*** that you require multi-factor authentication on your administrative account.</span></span> <span data-ttu-id="b2120-159">このスクリプトは、MFA 認証をサポートします。</span><span class="sxs-lookup"><span data-stu-id="b2120-159">This script supports MFA authentication.</span></span>

1. <span data-ttu-id="b2120-160">スクリプトを実行するコンピューターに、ローカル管理者権限を使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="b2120-160">Sign in to the computer that you will run the script from with local administrator rights.</span></span>

2. <span data-ttu-id="b2120-161">[Get-AzureADPSPermissions](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09)スクリプトを GitHub から、スクリプトを実行するフォルダーにダウンロードまたはコピーします。</span><span class="sxs-lookup"><span data-stu-id="b2120-161">Download or copy the [Get-AzureADPSPermissions.ps1](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09) script from GitHub to a folder from which you will run the script.</span></span> <span data-ttu-id="b2120-162">これは、出力 "permissions" ファイルが書き込まれるフォルダーと同じです。</span><span class="sxs-lookup"><span data-stu-id="b2120-162">This will be the same folder to which the output "permissions.csv" file will be written.</span></span>

3. <span data-ttu-id="b2120-163">管理者として PowerShell インスタンスを開き、スクリプトを保存したフォルダーを開きます。</span><span class="sxs-lookup"><span data-stu-id="b2120-163">Open a PowerShell instance as an administrator and open to the folder you saved the script to.</span></span>

4. <span data-ttu-id="b2120-164">[AzureAD](https://docs.microsoft.com/powershell/module/azuread/connect-azuread)コマンドレットを使用して、ディレクトリに接続します。</span><span class="sxs-lookup"><span data-stu-id="b2120-164">Connect to your directory using the [Connect-AzureAD](https://docs.microsoft.com/powershell/module/azuread/connect-azuread) cmdlet.</span></span>

5. <span data-ttu-id="b2120-165">次の PowerShell コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="b2120-165">Run this PowerShell command:</span></span>

   ```powershell
   Get-AzureADPSPermissions.ps1 | Export-csv -Path "Permissions.csv" -NoTypeInformation
   ```

<span data-ttu-id="b2120-166">スクリプトによって、Permissions という名前のファイルが1つ作成されます。</span><span class="sxs-lookup"><span data-stu-id="b2120-166">The script produces one file named Permissions.csv.</span></span> <span data-ttu-id="b2120-167">次の手順に従って、不法なアプリケーションアクセス許可の付与を検索します。</span><span class="sxs-lookup"><span data-stu-id="b2120-167">Follow these steps to look for illicit application permission grants:</span></span>

1. <span data-ttu-id="b2120-168">[Conな種類] 列 (列 G) で、値 "AllPrinciples" を検索します。</span><span class="sxs-lookup"><span data-stu-id="b2120-168">In the ConsentType column (column G) search for the value "AllPrinciples".</span></span> <span data-ttu-id="b2120-169">AllPrincipals アクセス許可によって、クライアントアプリケーションは、テナント内のすべてのユーザーのコンテンツにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="b2120-169">The AllPrincipals permission allows the client application to access everyone's content in the tenancy.</span></span> <span data-ttu-id="b2120-170">ネイティブの Microsoft 365 アプリケーションは、このアクセス許可を正しく動作させるために必要です。</span><span class="sxs-lookup"><span data-stu-id="b2120-170">Native Microsoft 365 applications need this permission to work correctly.</span></span> <span data-ttu-id="b2120-171">このアクセス許可を持つ Microsoft 以外のすべてのアプリケーションは、慎重にレビューする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b2120-171">Every non-Microsoft application with this permission should be reviewed carefully.</span></span>

2. <span data-ttu-id="b2120-172">[アクセス許可] 列 (列 F) に、各委任されたアプリケーションがコンテンツに対して持っているアクセス許可を確認します。</span><span class="sxs-lookup"><span data-stu-id="b2120-172">In the Permission column (column F) review the permissions that each delegated application has to content.</span></span> <span data-ttu-id="b2120-173">"読み取り" と "書き込み" アクセス許可または "\* を探します。All "アクセス許可を使用して、適切ではない可能性があるため慎重に確認してください。</span><span class="sxs-lookup"><span data-stu-id="b2120-173">Look for "Read" and "Write" permission or "\*.All" permission, and review these carefully because they may not be appropriate.</span></span>

3. <span data-ttu-id="b2120-174">同意が付与されている特定のユーザーを確認します。</span><span class="sxs-lookup"><span data-stu-id="b2120-174">Review the specific users that have consents granted.</span></span> <span data-ttu-id="b2120-175">プロファイルが大きい場合や、影響度の高いユーザーに不適切な同意が付与されている場合は、さらに詳しく調査する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b2120-175">If high profile or high impact users have inappropriate consents granted, you should investigate further.</span></span>

4. <span data-ttu-id="b2120-176">[ClientDisplayName] 列 (列 C) で、疑わしいと思われるアプリを探します。</span><span class="sxs-lookup"><span data-stu-id="b2120-176">In the ClientDisplayName column (column C) look for apps that seem suspicious.</span></span> <span data-ttu-id="b2120-177">名前のスペルが間違っているアプリ、super bland names、またはハッカーが発音した名前は、慎重に検討する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b2120-177">Apps with misspelled names, super bland names, or hacker-sounding names should be reviewed carefully.</span></span>

## <a name="determine-the-scope-of-the-attack"></a><span data-ttu-id="b2120-178">攻撃の範囲を決定する</span><span class="sxs-lookup"><span data-stu-id="b2120-178">Determine the scope of the attack</span></span>

<span data-ttu-id="b2120-179">アプリケーションアクセスのインベントリ処理が終了したら、**監査ログ**を確認して、違反の完全な範囲を特定します。</span><span class="sxs-lookup"><span data-stu-id="b2120-179">After you have finished inventorying application access, review the **audit log** to determine the full scope of the breach.</span></span> <span data-ttu-id="b2120-180">影響を受けるユーザー、不法アプリケーションが組織にアクセスした時間枠、およびアプリのアクセス許可を検索します。</span><span class="sxs-lookup"><span data-stu-id="b2120-180">Search on the affected users, the time frames that the illicit application had access to your organization, and the permissions the app had.</span></span> <span data-ttu-id="b2120-181">**監査ログ**は、 [Microsoft 365 セキュリティ/コンプライアンスセンター](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)で検索できます。</span><span class="sxs-lookup"><span data-stu-id="b2120-181">You can search the **audit log** in the [Microsoft 365 Security and Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b2120-182">この情報を取得するには、攻撃の前に、[管理者とユーザーの](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off)[メールボックスの監査](https://docs.microsoft.com/microsoft-365/compliance/enable-mailbox-auditing)とアクティビティの監査を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b2120-182">[Mailbox auditing](https://docs.microsoft.com/microsoft-365/compliance/enable-mailbox-auditing) and [Activity auditing for admins and users](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off) must have been enabled prior to the attack for you to get this information.</span></span>

## <a name="how-to-stop-and-remediate-an-illicit-consent-grant-attack"></a><span data-ttu-id="b2120-183">方法不法な同意の付与攻撃を停止および修復する方法</span><span class="sxs-lookup"><span data-stu-id="b2120-183">How to stop and remediate an illicit consent grant attack</span></span>

<span data-ttu-id="b2120-184">不法なアクセス許可を使用してアプリケーションを識別した後、そのアクセスを削除する方法がいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="b2120-184">After you have identified an application with illicit permissions, you have several ways to remove that access.</span></span>

- <span data-ttu-id="b2120-185">Azure Active Directory ポータルのアプリケーションのアクセス許可は、次の方法で取り消すことができます。</span><span class="sxs-lookup"><span data-stu-id="b2120-185">You can revoke the application's permission in the Azure Active Directory Portal by:</span></span>

  - <span data-ttu-id="b2120-186">**Azure Active Directory ユーザー**ブレードの影響を受けるユーザーに移動します。</span><span class="sxs-lookup"><span data-stu-id="b2120-186">Navigate to the affected user in the **Azure Active Directory User** blade.</span></span>

  - <span data-ttu-id="b2120-187">[**アプリケーション**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b2120-187">Select **Applications**.</span></span>

  - <span data-ttu-id="b2120-188">違法アプリケーションを選択します。</span><span class="sxs-lookup"><span data-stu-id="b2120-188">Select the illicit application.</span></span>

  - <span data-ttu-id="b2120-189">ドリルダウンで [**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b2120-189">Click **Remove** in the drill down.</span></span>

- <span data-ttu-id="b2120-190">PowerShell で OAuth 同意の付与を取り消すには、 [AzureADOAuth2PermissionGrant](https://docs.microsoft.com/powershell/module/azuread/Remove-AzureADOAuth2PermissionGrant)の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="b2120-190">You can revoke the OAuth consent grant with PowerShell by following the steps in [Remove-AzureADOAuth2PermissionGrant](https://docs.microsoft.com/powershell/module/azuread/Remove-AzureADOAuth2PermissionGrant).</span></span>

- <span data-ttu-id="b2120-191">PowerShell を使用してサービスアプリの役割の割り当てを無効にするには、 [AzureADServiceAppRoleAssignment](https://docs.microsoft.com/powershell/module/azuread/Remove-AzureADServiceAppRoleAssignment)の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="b2120-191">You can revoke the Service App Role Assignment with PowerShell by following the steps in [Remove-AzureADServiceAppRoleAssignment](https://docs.microsoft.com/powershell/module/azuread/Remove-AzureADServiceAppRoleAssignment).</span></span>

- <span data-ttu-id="b2120-192">影響を受けるアカウントのサインインを完全に無効にすることもできます。これにより、そのアカウントのデータに対するアプリのアクセスが無効になります。</span><span class="sxs-lookup"><span data-stu-id="b2120-192">You can also disable sign-in for the affected account altogether, which will in turn disable app access to data in that account.</span></span> <span data-ttu-id="b2120-193">これは、エンドユーザーの生産性を向上させるのには理想的ではありませんが、影響をすばやく抑えるために作業する場合は、実用的な短期的な修復になります。</span><span class="sxs-lookup"><span data-stu-id="b2120-193">This isn't ideal for the end user's productivity, of course, but if you are working to limit impact quickly, it can be a viable short-term remediation.</span></span>

- <span data-ttu-id="b2120-194">テナントのために統合アプリケーションをオフにすることができます。</span><span class="sxs-lookup"><span data-stu-id="b2120-194">You can turn integrated applications off for your tenancy.</span></span> <span data-ttu-id="b2120-195">これは、エンドユーザーがテナント全体に同意を付与する機能を無効にする重大な手順です。</span><span class="sxs-lookup"><span data-stu-id="b2120-195">This is a drastic step that disables the ability for end users to grant consent on a tenant-wide basis.</span></span> <span data-ttu-id="b2120-196">これにより、ユーザーが悪意のあるアプリケーションへのアクセスを誤って許可するのを防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="b2120-196">This prevents your users from inadvertently granting access to a malicious application.</span></span> <span data-ttu-id="b2120-197">これは、ユーザーがサードパーティ製のアプリケーションを使用して生産性を向上させることがひどくないため、強くお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="b2120-197">This isn't strongly recommended as it severely impairs your users' ability to be productive with third party applications.</span></span> <span data-ttu-id="b2120-198">これを行うには、[統合アプリをオンまたはオフ](https://docs.microsoft.com/office365/admin/misc/integrated-apps)にする手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="b2120-198">You can do this by following the steps in [Turning Integrated Apps on or off](https://docs.microsoft.com/office365/admin/misc/integrated-apps).</span></span>

## <a name="secure-microsoft-365-like-a-cybersecurity-pro"></a><span data-ttu-id="b2120-199">サイバー セキュリティの専門家のように、Microsoft 365 のセキュリティを強化する</span><span class="sxs-lookup"><span data-stu-id="b2120-199">Secure Microsoft 365 like a cybersecurity pro</span></span>

<span data-ttu-id="b2120-200">Microsoft 365 サブスクリプションには、データとユーザーを保護するために使用できる強力なセキュリティ機能のセットが用意されています。</span><span class="sxs-lookup"><span data-stu-id="b2120-200">Your Microsoft 365 subscription comes with a powerful set of security capabilities that you can use to protect your data and your users.</span></span> <span data-ttu-id="b2120-201">[Microsoft 365 セキュリティ ロードマップ - 最初の 30 日間、90 日間、およびそれ以降の最優先事項](security-roadmap.md)を使用して、Microsoft 365 テナントをセキュリティで保護するために Microsoft が推奨するベスト プラクティスを実装します。</span><span class="sxs-lookup"><span data-stu-id="b2120-201">Use the [Microsoft 365 security roadmap - Top priorities for the first 30 days, 90 days, and beyond](security-roadmap.md) to implement Microsoft recommended best practices for securing your Microsoft 365 tenant.</span></span>

- <span data-ttu-id="b2120-202">最初の30日間に実行するタスク。</span><span class="sxs-lookup"><span data-stu-id="b2120-202">Tasks to accomplish in the first 30 days.</span></span> <span data-ttu-id="b2120-203">これらはすぐに影響を受け、ユーザーにとって影響が小さくなります。</span><span class="sxs-lookup"><span data-stu-id="b2120-203">These have immediate affect and are low-impact to your users.</span></span>

- <span data-ttu-id="b2120-p124">最初の 90 日間で完了すべき作業。作業の計画と実装に少し時間がかかりますが、セキュリティ体制は大幅に向上します。</span><span class="sxs-lookup"><span data-stu-id="b2120-p124">Tasks to accomplish in 90 days. These take a bit more time to plan and implement but greatly improve your security posture.</span></span>

- <span data-ttu-id="b2120-p125">90 日以降。最初の 90 日間の作業で保護が強化されます。</span><span class="sxs-lookup"><span data-stu-id="b2120-p125">Beyond 90 days. These enhancements build in your first 90 days work.</span></span>

## <a name="see-also"></a><span data-ttu-id="b2120-208">関連項目:</span><span class="sxs-lookup"><span data-stu-id="b2120-208">See also:</span></span>

- <span data-ttu-id="b2120-209">[[自分のアプリケーション] リスト内の予期しないアプリケーション](https://docs.microsoft.com/azure/active-directory/application-access-unexpected-application)は、データにアクセスするための予期しないアプリケーションがあることを認識した後に、管理者がさまざまなアクションを実行できるようにします。</span><span class="sxs-lookup"><span data-stu-id="b2120-209">[Unexpected application in my applications list](https://docs.microsoft.com/azure/active-directory/application-access-unexpected-application) walks administrators through various actions they may want to take after realizing there are unexpected applications with access to data.</span></span>

- <span data-ttu-id="b2120-210">[アプリケーションを Azure Active Directory と統合](https://docs.microsoft.com/azure/active-directory/active-directory-apps-permissions-consent)することは、同意とアクセス許可の概要です。</span><span class="sxs-lookup"><span data-stu-id="b2120-210">[Integrating applications with Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-apps-permissions-consent) is a high-level overview of consent and permissions.</span></span>

- <span data-ttu-id="b2120-211">[アプリケーションの開発に関する問題](https://docs.microsoft.com/azure/active-directory/active-directory-application-dev-development-content-map)さまざまな同意に関する記事へのリンクを提供します。</span><span class="sxs-lookup"><span data-stu-id="b2120-211">[Problems developing my application](https://docs.microsoft.com/azure/active-directory/active-directory-application-dev-development-content-map) provides links to various consent related articles.</span></span>

- <span data-ttu-id="b2120-212">「 [Azure Active Directory のアプリケーションおよびサービスプリンシパルオブジェクト (AZURE AD)」で](https://docs.microsoft.com/azure/active-directory/develop/active-directory-application-objects)は、アプリケーションモデルにとって中核となるアプリケーションおよびサービスプリンシパルオブジェクトの概要を示します。</span><span class="sxs-lookup"><span data-stu-id="b2120-212">[Application and service principal objects in Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/develop/active-directory-application-objects) provides an overview of the Application and Service principal objects that are core to the application model.</span></span>

- <span data-ttu-id="b2120-213">アプリへの[アクセスを管理](https://docs.microsoft.com/azure/active-directory/active-directory-managing-access-to-apps)すると、管理者がアプリへのユーザーアクセスを管理するために必要な機能の概要が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b2120-213">[Manage access to apps](https://docs.microsoft.com/azure/active-directory/active-directory-managing-access-to-apps) is an overview of the capabilities that administrators have to manage user access to apps.</span></span>
