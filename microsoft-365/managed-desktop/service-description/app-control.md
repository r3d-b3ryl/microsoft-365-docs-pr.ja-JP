---
title: アプリ コントロール
description: アプリケーションの制御と信頼を使用する方法
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 6f5cc923b5a18b1f45dd186e88228db8c3a891cc
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841305"
---
# <a name="app-control"></a><span data-ttu-id="3e296-104">アプリ コントロール</span><span class="sxs-lookup"><span data-stu-id="3e296-104">App control</span></span>

<span data-ttu-id="3e296-105">アプリ制御は、クライアント デバイスでのコードの実行を制限する Microsoft マネージド デスクトップのオプションのセキュリティプラクティスです。</span><span class="sxs-lookup"><span data-stu-id="3e296-105">App control is an optional security practice in Microsoft Managed Desktop that restricts the execution of code on client devices.</span></span> <span data-ttu-id="3e296-106">このコントロールは、顧客承認済みの発行元リストによって署名されたコードのみを実行する必要が生じ、マルウェアや悪意のあるスクリプトのリスクを軽減します。</span><span class="sxs-lookup"><span data-stu-id="3e296-106">This control mitigates the risk of malware or malicious scripts by requiring that only code signed by a customer-approved list of publishers can run.</span></span> <span data-ttu-id="3e296-107">この制御には多くのセキュリティ上の利点がありますが、主にクライアント ベースの悪用からデータと ID を保護することです。</span><span class="sxs-lookup"><span data-stu-id="3e296-107">There are many security benefits from this control, but it primarily aims to protect data and identity from client-based exploits.</span></span>

<span data-ttu-id="3e296-108">Microsoft マネージド デスクトップは、コア生産性シナリオを可能にする基本ポリシーを作成することで、アプリ制御ポリシーの管理を簡素化します。</span><span class="sxs-lookup"><span data-stu-id="3e296-108">Microsoft Managed Desktop simplifies the management of app control policies by creating a base policy that enables core productivity scenarios.</span></span> <span data-ttu-id="3e296-109">環境内のアプリとスクリプトに固有の他の署名者に対する信頼を拡張できます。</span><span class="sxs-lookup"><span data-stu-id="3e296-109">You can extend trust to other signers that are specific to the apps and scripts in your environment.</span></span> 


<span data-ttu-id="3e296-110">どのセキュリティ テクノロジでも、ユーザー エクスペリエンス、セキュリティ、およびコストのバランスが必要です。</span><span class="sxs-lookup"><span data-stu-id="3e296-110">Any security technology requires a balance among user experience, security, and cost.</span></span> <span data-ttu-id="3e296-111">アプリの制御は、環境内の悪意のあるソフトウェアの脅威を軽減しますが、ユーザーに影響を及び、IT 管理者に対する追加のアクションが行えます。</span><span class="sxs-lookup"><span data-stu-id="3e296-111">App control reduces the threat of malicious software in your environment, but there are consequences to the user and further actions for your IT administrator.</span></span>

<span data-ttu-id="3e296-112">**追加のセキュリティ:**</span><span class="sxs-lookup"><span data-stu-id="3e296-112">**Additional security:**</span></span>

<span data-ttu-id="3e296-113">アプリ制御ポリシーによって信頼されていないアプリまたはスクリプトは、デバイスでの実行がブロックされます。</span><span class="sxs-lookup"><span data-stu-id="3e296-113">Apps or scripts that are not trusted by the app control policy are blocked from running on devices.</span></span>

<span data-ttu-id="3e296-114">**追加の責任:**</span><span class="sxs-lookup"><span data-stu-id="3e296-114">**Your additional responsibilities:**</span></span>

- <span data-ttu-id="3e296-115">アプリをテストして、アプリケーション制御ポリシーによってブロックされるかどうかを特定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3e296-115">You are responsible for testing your apps to identify whether they would be blocked by the application control policy.</span></span>
- <span data-ttu-id="3e296-116">アプリがブロックされている (またはブロックされる) 場合は、必要な署名者の詳細を特定し、管理ポータルから変更を要求する責任があります。</span><span class="sxs-lookup"><span data-stu-id="3e296-116">If an app is (or would be) blocked, you are responsible for identifying the needed signer details and requesting a change through the Admin portal.</span></span>

<span data-ttu-id="3e296-117">**Microsoft マネージド デスクトップの責任:**</span><span class="sxs-lookup"><span data-stu-id="3e296-117">**Microsoft Managed Desktop responsibilities:**</span></span>

- <span data-ttu-id="3e296-118">Microsoft マネージド デスクトップは、M365 アプリ、Windows、Teams、OneDrive など、Microsoft のコア製品を有効にする基本ポリシーを維持しています。</span><span class="sxs-lookup"><span data-stu-id="3e296-118">Microsoft Managed Desktop maintains the base policy that enables core Microsoft products like M365 Apps, Windows, Teams, OneDrive, and so on.</span></span>
- <span data-ttu-id="3e296-119">Microsoft マネージド デスクトップは、信頼できる署名者を挿入し、更新されたポリシーをデバイスに展開します。</span><span class="sxs-lookup"><span data-stu-id="3e296-119">Microsoft Managed Desktop inserts your trusted signers and deploys the updated policy to your devices.</span></span>


## <a name="managing-trust-in-applications"></a><span data-ttu-id="3e296-120">アプリケーションの信頼の管理</span><span class="sxs-lookup"><span data-stu-id="3e296-120">Managing trust in applications</span></span>

<span data-ttu-id="3e296-121">Microsoft マネージド デスクトップは、Microsoft テクノロジのコア コンポーネントを信頼する基本ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="3e296-121">Microsoft Managed Desktop curates a base policy that trusts the core components of Microsoft technologies.</span></span> <span data-ttu-id="3e296-122">次に *、Microsoft* マネージド デスクトップに既に信頼しているアプリケーションとスクリプトを通知することで、独自のアプリケーションとスクリプトの信頼を追加します。</span><span class="sxs-lookup"><span data-stu-id="3e296-122">You then *add* trust for your own applications and scripts by informing Microsoft Managed Desktop which of them you already trust.</span></span>

### <a name="base-policy"></a><span data-ttu-id="3e296-123">基本ポリシー</span><span class="sxs-lookup"><span data-stu-id="3e296-123">Base policy</span></span>

<span data-ttu-id="3e296-124">Microsoft マネージド デスクトップは、Microsoft サイバーセキュリティの専門家と共同で、コードのコンパイルや信頼できないファイルの実行などの危険なアクティビティをブロックしながら、Microsoft Intune 経由で展開されるほとんどのアプリを有効にする標準ポリシーを作成し、維持します。</span><span class="sxs-lookup"><span data-stu-id="3e296-124">Microsoft Managed Desktop, in collaboration with Microsoft cybersecurity experts, creates, and maintains a standard policy that enables most apps deployed through Microsoft Intune while blocking dangerous activities like code compilation or execution of untrusted files.</span></span>

<span data-ttu-id="3e296-125">基本ポリシーは、ソフトウェアの実行を制限するために次のアプローチを採用します。</span><span class="sxs-lookup"><span data-stu-id="3e296-125">The base policy takes the following approach to restricting software execution:</span></span>

- <span data-ttu-id="3e296-126">管理者が実行するファイルの実行が許可されます。</span><span class="sxs-lookup"><span data-stu-id="3e296-126">Files run by administrators will be allowed to run.</span></span>
- <span data-ttu-id="3e296-127">ユーザーが書き込み *可能な* ディレクトリに含められない場所にあるファイルの実行が許可されます。</span><span class="sxs-lookup"><span data-stu-id="3e296-127">Files in locations that are *not* in user-writable directories will be allowed to run.</span></span>
- <span data-ttu-id="3e296-128">ファイルは、信頼できる署名 [者によって署名されます](#signer-requests)。</span><span class="sxs-lookup"><span data-stu-id="3e296-128">Files are signed by a [trusted signer](#signer-requests).</span></span>
- <span data-ttu-id="3e296-129">Microsoft によって署名されたほとんどのファイルは実行されます。ただし、コードのコンパイルなど、リスクの高いアクションを防ぐためにブロックされるファイルがあります。</span><span class="sxs-lookup"><span data-stu-id="3e296-129">Most files signed by Microsoft will run, however some are blocked to prevent high-risk actions like code compilation.</span></span>


<span data-ttu-id="3e296-130">管理者以外のユーザーがアプリまたはスクリプトをデバイスに追加した可能性がある場合 (つまり、ユーザーが書き込み可能なディレクトリに存在する場合)、管理者によって特に許可されていない限り、実行は許可されません。</span><span class="sxs-lookup"><span data-stu-id="3e296-130">If a user other than an administrator could have added an app or script to a device (that is, it's in a user-writable directory), we won't allow it to execute unless it has already been specifically allowed by an administrator.</span></span> <span data-ttu-id="3e296-131">ユーザーがマルウェアをインストールしようとした場合、ユーザーが実行するアプリの脆弱性がマルウェアのインストールを試みる場合、またはユーザーが意図的に承認されていないアプリまたはスクリプトを実行しようとした場合、ポリシーは実行を停止します。</span><span class="sxs-lookup"><span data-stu-id="3e296-131">If a user is tricked into trying to install malware, if a vulnerability in an app the user runs attempts to install malware, or if a user intentionally tries to run an unauthorized app or script, our policy will stop execution.</span></span>

### <a name="signer-requests"></a><span data-ttu-id="3e296-132">署名者要求</span><span class="sxs-lookup"><span data-stu-id="3e296-132">Signer requests</span></span>

<span data-ttu-id="3e296-133">署名者の要求を提出して、信頼できるソフトウェア発行元によって提供されるアプリ *を通知します*。</span><span class="sxs-lookup"><span data-stu-id="3e296-133">You inform us of which apps are provided by software publishers you trust by filing a *signer request*.</span></span> <span data-ttu-id="3e296-134">これにより、ベースライン アプリケーション制御ポリシーに信頼情報が追加され、その発行元の証明書で署名されたソフトウェアがデバイスで実行されます。</span><span class="sxs-lookup"><span data-stu-id="3e296-134">By doing so, we add that trust information into the baseline application control policy and allow any software signed with that publisher's certificate to run on your devices.</span></span>

## <a name="audit-and-enforced-policies"></a><span data-ttu-id="3e296-135">監査ポリシーと実施ポリシー</span><span class="sxs-lookup"><span data-stu-id="3e296-135">Audit and Enforced policies</span></span>

<span data-ttu-id="3e296-136">Microsoft マネージド デスクトップでは、次の 2 つの Microsoft Intune ポリシーを使用してアプリを制御します。</span><span class="sxs-lookup"><span data-stu-id="3e296-136">Microsoft Managed Desktop uses two Microsoft Intune policies to provide app control:</span></span>

### <a name="audit-policy"></a><span data-ttu-id="3e296-137">監査ポリシー</span><span class="sxs-lookup"><span data-stu-id="3e296-137">Audit policy</span></span>
<span data-ttu-id="3e296-138">このポリシーは、アプリまたはスクリプトが強制ポリシーによってブロックされるかどうかを記録するログを作成します。</span><span class="sxs-lookup"><span data-stu-id="3e296-138">This policy creates logs to record whether an app or script would be blocked by the Enforced policy.</span></span> <span data-ttu-id="3e296-139">監査ポリシーは、アプリ制御ルールを適用しません。また、アプリケーションが発行元の除外を必要とするかどうかを特定するためのテスト用です。</span><span class="sxs-lookup"><span data-stu-id="3e296-139">Audit policies don't enforce app control rules and are meant for testing purposes to identify whether an application will require a publisher exemption.</span></span> <span data-ttu-id="3e296-140">イベント ビューアーに警告 (8003 または 8006 イベント) が記録されます。イベント ビューアーでは、指定したアプリまたはスクリプトの実行やインストールをブロックしません。</span><span class="sxs-lookup"><span data-stu-id="3e296-140">It logs warnings (8003 or 8006 events) in Event Viewer instead of blocking the execution or installation of specified apps or script.</span></span>

### <a name="enforced-policy"></a><span data-ttu-id="3e296-141">実施されたポリシー</span><span class="sxs-lookup"><span data-stu-id="3e296-141">Enforced policy</span></span>
<span data-ttu-id="3e296-142">このポリシーは、信頼されていないアプリやスクリプトの実行をブロックし、アプリまたはスクリプトがブロックされるたびにログを作成します。</span><span class="sxs-lookup"><span data-stu-id="3e296-142">This policy blocks untrusted apps and scripts from running and creates logs whenever an app or script is blocked.</span></span> <span data-ttu-id="3e296-143">実施されたポリシーにより、標準ユーザーは、ユーザーが書き込み可能なディレクトリに格納されているアプリやスクリプトを実行できません。</span><span class="sxs-lookup"><span data-stu-id="3e296-143">Enforced policies prevent standard users from executing apps or scripts stored in user-writable directories.</span></span>

<span data-ttu-id="3e296-144">テスト グループ内のデバイスには監査ポリシーが適用され、それらを使用して、アプリケーションが問題を引き起こすかどうかを検証できます。</span><span class="sxs-lookup"><span data-stu-id="3e296-144">Devices in the Test group have an Audit policy applied so that you can use them to validate whether any applications will cause issues.</span></span> <span data-ttu-id="3e296-145">他のすべてのグループ (First、Fast、Broad) では強制ポリシーが使用されます。そのため、これらのグループのユーザーは、信頼されていないアプリやスクリプトを実行できません。</span><span class="sxs-lookup"><span data-stu-id="3e296-145">All other groups (First, Fast, and Broad) use an Enforced policy, so users in those groups won't be able to run untrusted apps or scripts.</span></span>







