---
title: アプリ コントロール
description: アプリケーションでアプリコントロールと信頼を使用する方法
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
# <a name="app-control"></a><span data-ttu-id="0db6c-104">アプリ コントロール</span><span class="sxs-lookup"><span data-stu-id="0db6c-104">App control</span></span>

<span data-ttu-id="0db6c-105">アプリコントロールは、クライアント デバイスでのコードの実行を制限する Microsoft Managed Desktop のオプションのセキュリティプラクティスです。</span><span class="sxs-lookup"><span data-stu-id="0db6c-105">App control is an optional security practice in Microsoft Managed Desktop that restricts the execution of code on client devices.</span></span> <span data-ttu-id="0db6c-106">このコントロールは、お客様が承認した発行元リストによって署名されたコードのみを実行する必要が生じ、マルウェアや悪意のあるスクリプトのリスクを軽減します。</span><span class="sxs-lookup"><span data-stu-id="0db6c-106">This control mitigates the risk of malware or malicious scripts by requiring that only code signed by a customer-approved list of publishers can run.</span></span> <span data-ttu-id="0db6c-107">このコントロールには多くのセキュリティ上の利点がありますが、主にクライアント ベースの悪用からデータと ID を保護することです。</span><span class="sxs-lookup"><span data-stu-id="0db6c-107">There are many security benefits from this control, but it primarily aims to protect data and identity from client-based exploits.</span></span>

<span data-ttu-id="0db6c-108">Microsoft Managed Desktop は、コア生産性シナリオを可能にする基本ポリシーを作成することで、アプリ制御ポリシーの管理を簡素化します。</span><span class="sxs-lookup"><span data-stu-id="0db6c-108">Microsoft Managed Desktop simplifies the management of app control policies by creating a base policy that enables core productivity scenarios.</span></span> <span data-ttu-id="0db6c-109">環境内のアプリとスクリプトに固有の他の署名者に信頼を拡張できます。</span><span class="sxs-lookup"><span data-stu-id="0db6c-109">You can extend trust to other signers that are specific to the apps and scripts in your environment.</span></span> 


<span data-ttu-id="0db6c-110">セキュリティ テクノロジには、ユーザー エクスペリエンス、セキュリティ、コストのバランスが必要です。</span><span class="sxs-lookup"><span data-stu-id="0db6c-110">Any security technology requires a balance among user experience, security, and cost.</span></span> <span data-ttu-id="0db6c-111">アプリ制御は、環境内の悪意のあるソフトウェアの脅威を軽減しますが、ユーザーに影響を及び、IT 管理者に対するさらなるアクションがあります。</span><span class="sxs-lookup"><span data-stu-id="0db6c-111">App control reduces the threat of malicious software in your environment, but there are consequences to the user and further actions for your IT administrator.</span></span>

<span data-ttu-id="0db6c-112">**追加のセキュリティ:**</span><span class="sxs-lookup"><span data-stu-id="0db6c-112">**Additional security:**</span></span>

<span data-ttu-id="0db6c-113">アプリコントロール ポリシーによって信頼されていないアプリまたはスクリプトは、デバイスでの実行がブロックされます。</span><span class="sxs-lookup"><span data-stu-id="0db6c-113">Apps or scripts that are not trusted by the app control policy are blocked from running on devices.</span></span>

<span data-ttu-id="0db6c-114">**追加の責任:**</span><span class="sxs-lookup"><span data-stu-id="0db6c-114">**Your additional responsibilities:**</span></span>

- <span data-ttu-id="0db6c-115">アプリをテストして、アプリがアプリケーション制御ポリシーによってブロックされるかどうかを確認する責任があります。</span><span class="sxs-lookup"><span data-stu-id="0db6c-115">You are responsible for testing your apps to identify whether they would be blocked by the application control policy.</span></span>
- <span data-ttu-id="0db6c-116">アプリがブロックされている (またはブロックされる) 場合は、必要な署名者の詳細を特定し、管理者ポータルを通じて変更を要求する責任があります。</span><span class="sxs-lookup"><span data-stu-id="0db6c-116">If an app is (or would be) blocked, you are responsible for identifying the needed signer details and requesting a change through the Admin portal.</span></span>

<span data-ttu-id="0db6c-117">**Microsoft Managed Desktop の責任:**</span><span class="sxs-lookup"><span data-stu-id="0db6c-117">**Microsoft Managed Desktop responsibilities:**</span></span>

- <span data-ttu-id="0db6c-118">Microsoft Managed Desktop は、M365 Apps、Windows、Teams、OneDrive など、Microsoft のコア製品を有効にする基本ポリシーを維持しています。</span><span class="sxs-lookup"><span data-stu-id="0db6c-118">Microsoft Managed Desktop maintains the base policy that enables core Microsoft products like M365 Apps, Windows, Teams, OneDrive, and so on.</span></span>
- <span data-ttu-id="0db6c-119">Microsoft Managed Desktop は、信頼できる署名者を挿入し、更新されたポリシーをデバイスに展開します。</span><span class="sxs-lookup"><span data-stu-id="0db6c-119">Microsoft Managed Desktop inserts your trusted signers and deploys the updated policy to your devices.</span></span>


## <a name="managing-trust-in-applications"></a><span data-ttu-id="0db6c-120">アプリケーションの信頼の管理</span><span class="sxs-lookup"><span data-stu-id="0db6c-120">Managing trust in applications</span></span>

<span data-ttu-id="0db6c-121">Microsoft Managed Desktop は、Microsoft テクノロジのコア コンポーネントを信頼する基本ポリシーを管理します。</span><span class="sxs-lookup"><span data-stu-id="0db6c-121">Microsoft Managed Desktop curates a base policy that trusts the core components of Microsoft technologies.</span></span> <span data-ttu-id="0db6c-122">その後 *、既* に信頼しているアプリケーションとスクリプトを Microsoft Managed Desktop に通知することで、独自のアプリケーションとスクリプトに対する信頼を追加します。</span><span class="sxs-lookup"><span data-stu-id="0db6c-122">You then *add* trust for your own applications and scripts by informing Microsoft Managed Desktop which of them you already trust.</span></span>

### <a name="base-policy"></a><span data-ttu-id="0db6c-123">基本ポリシー</span><span class="sxs-lookup"><span data-stu-id="0db6c-123">Base policy</span></span>

<span data-ttu-id="0db6c-124">Microsoft Managed Desktop は、Microsoft サイバーセキュリティの専門家と共同で、コードのコンパイルや信頼されていないファイルの実行などの危険なアクティビティをブロックしながら、Microsoft Intune を通じて展開されるほとんどのアプリを有効にする標準ポリシーを作成し、維持します。</span><span class="sxs-lookup"><span data-stu-id="0db6c-124">Microsoft Managed Desktop, in collaboration with Microsoft cybersecurity experts, creates, and maintains a standard policy that enables most apps deployed through Microsoft Intune while blocking dangerous activities like code compilation or execution of untrusted files.</span></span>

<span data-ttu-id="0db6c-125">基本ポリシーは、ソフトウェアの実行を制限するために次の方法を採用します。</span><span class="sxs-lookup"><span data-stu-id="0db6c-125">The base policy takes the following approach to restricting software execution:</span></span>

- <span data-ttu-id="0db6c-126">管理者が実行するファイルの実行が許可されます。</span><span class="sxs-lookup"><span data-stu-id="0db6c-126">Files run by administrators will be allowed to run.</span></span>
- <span data-ttu-id="0db6c-127">ユーザーが書き込み *可能な* ディレクトリに含められない場所にあるファイルの実行が許可されます。</span><span class="sxs-lookup"><span data-stu-id="0db6c-127">Files in locations that are *not* in user-writable directories will be allowed to run.</span></span>
- <span data-ttu-id="0db6c-128">ファイルは、信頼できる署名者 [によって署名されます](#signer-requests)。</span><span class="sxs-lookup"><span data-stu-id="0db6c-128">Files are signed by a [trusted signer](#signer-requests).</span></span>
- <span data-ttu-id="0db6c-129">Microsoft によって署名されたほとんどのファイルが実行されます。ただし、コードのコンパイルのようなリスクの高いアクションを防ぐためにブロックされるファイルがあります。</span><span class="sxs-lookup"><span data-stu-id="0db6c-129">Most files signed by Microsoft will run, however some are blocked to prevent high-risk actions like code compilation.</span></span>


<span data-ttu-id="0db6c-130">管理者以外のユーザーがアプリまたはスクリプトをデバイスに追加した (つまり、ユーザーが書き込み可能なディレクトリにある) 場合、管理者が特に許可していない限り、実行を許可されません。</span><span class="sxs-lookup"><span data-stu-id="0db6c-130">If a user other than an administrator could have added an app or script to a device (that is, it's in a user-writable directory), we won't allow it to execute unless it has already been specifically allowed by an administrator.</span></span> <span data-ttu-id="0db6c-131">ユーザーがマルウェアのインストールを試みようとした場合、ユーザーが実行するアプリの脆弱性がマルウェアのインストールを試みる場合、またはユーザーが意図的に承認されていないアプリまたはスクリプトを実行しようとした場合、ポリシーは実行を停止します。</span><span class="sxs-lookup"><span data-stu-id="0db6c-131">If a user is tricked into trying to install malware, if a vulnerability in an app the user runs attempts to install malware, or if a user intentionally tries to run an unauthorized app or script, our policy will stop execution.</span></span>

### <a name="signer-requests"></a><span data-ttu-id="0db6c-132">署名者の要求</span><span class="sxs-lookup"><span data-stu-id="0db6c-132">Signer requests</span></span>

<span data-ttu-id="0db6c-133">署名者要求を提出することで、信頼できるソフトウェア発行元によって提供されるアプリ *を通知します*。</span><span class="sxs-lookup"><span data-stu-id="0db6c-133">You inform us of which apps are provided by software publishers you trust by filing a *signer request*.</span></span> <span data-ttu-id="0db6c-134">これにより、その信頼情報をベースライン アプリケーション制御ポリシーに追加し、その発行元の証明書で署名されたソフトウェアをデバイスで実行できます。</span><span class="sxs-lookup"><span data-stu-id="0db6c-134">By doing so, we add that trust information into the baseline application control policy and allow any software signed with that publisher's certificate to run on your devices.</span></span>

## <a name="audit-and-enforced-policies"></a><span data-ttu-id="0db6c-135">監査ポリシーと適用ポリシー</span><span class="sxs-lookup"><span data-stu-id="0db6c-135">Audit and Enforced policies</span></span>

<span data-ttu-id="0db6c-136">Microsoft Managed Desktop では、次の 2 つの Microsoft Intune ポリシーを使用してアプリ制御を提供します。</span><span class="sxs-lookup"><span data-stu-id="0db6c-136">Microsoft Managed Desktop uses two Microsoft Intune policies to provide app control:</span></span>

### <a name="audit-policy"></a><span data-ttu-id="0db6c-137">監査ポリシー</span><span class="sxs-lookup"><span data-stu-id="0db6c-137">Audit policy</span></span>
<span data-ttu-id="0db6c-138">このポリシーは、アプリまたはスクリプトが強制ポリシーによってブロックされるかどうかを記録するログを作成します。</span><span class="sxs-lookup"><span data-stu-id="0db6c-138">This policy creates logs to record whether an app or script would be blocked by the Enforced policy.</span></span> <span data-ttu-id="0db6c-139">監査ポリシーはアプリ制御ルールを適用しません。また、アプリケーションが発行者の除外を必要とするかどうかを特定するためのテスト目的を目的とします。</span><span class="sxs-lookup"><span data-stu-id="0db6c-139">Audit policies don't enforce app control rules and are meant for testing purposes to identify whether an application will require a publisher exemption.</span></span> <span data-ttu-id="0db6c-140">指定したアプリまたはスクリプトの実行またはインストールをブロックするのではなく、イベント ビューアーに警告 (8003 イベントまたは 8006 イベント) を記録します。</span><span class="sxs-lookup"><span data-stu-id="0db6c-140">It logs warnings (8003 or 8006 events) in Event Viewer instead of blocking the execution or installation of specified apps or script.</span></span>

### <a name="enforced-policy"></a><span data-ttu-id="0db6c-141">ポリシーの適用</span><span class="sxs-lookup"><span data-stu-id="0db6c-141">Enforced policy</span></span>
<span data-ttu-id="0db6c-142">このポリシーは、信頼されていないアプリとスクリプトの実行をブロックし、アプリまたはスクリプトがブロックされるたびにログを作成します。</span><span class="sxs-lookup"><span data-stu-id="0db6c-142">This policy blocks untrusted apps and scripts from running and creates logs whenever an app or script is blocked.</span></span> <span data-ttu-id="0db6c-143">ポリシーを適用すると、標準ユーザーはユーザー書き込み可能なディレクトリに保存されているアプリやスクリプトを実行できません。</span><span class="sxs-lookup"><span data-stu-id="0db6c-143">Enforced policies prevent standard users from executing apps or scripts stored in user-writable directories.</span></span>

<span data-ttu-id="0db6c-144">テスト グループ内のデバイスには監査ポリシーが適用され、アプリケーションが問題を引き起こすかどうかを検証するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="0db6c-144">Devices in the Test group have an Audit policy applied so that you can use them to validate whether any applications will cause issues.</span></span> <span data-ttu-id="0db6c-145">他のすべてのグループ (First、Fast、および Broad) は、強制ポリシーを使用します。そのため、これらのグループのユーザーは信頼されていないアプリやスクリプトを実行できません。</span><span class="sxs-lookup"><span data-stu-id="0db6c-145">All other groups (First, Fast, and Broad) use an Enforced policy, so users in those groups won't be able to run untrusted apps or scripts.</span></span>







