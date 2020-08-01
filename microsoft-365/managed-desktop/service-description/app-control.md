---
title: アプリコントロール
description: ''
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: f11c7a4aa69c96232a33c565e7bf20d04b96d1f7
ms.sourcegitcommit: 126d22d8abd190beb7101f14bd357005e4c729f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2020
ms.locfileid: "46529973"
---
# <a name="app-control"></a><span data-ttu-id="a7fa0-103">アプリコントロール</span><span class="sxs-lookup"><span data-stu-id="a7fa0-103">App control</span></span>

<span data-ttu-id="a7fa0-104">アプリコントロールは、クライアントデバイスでのコードの実行を制限する Microsoft マネージドデスクトップのオプションのセキュリティプラクティスです。</span><span class="sxs-lookup"><span data-stu-id="a7fa0-104">App control is an optional security practice in Microsoft Managed Desktop that restricts the execution of code on client devices.</span></span> <span data-ttu-id="a7fa0-105">この制御により、マルウェアまたは悪意のあるスクリプトのリスクが軽減されます。これにより、お客様が承認した発行元のリストで署名されたコードのみを実行できるようになります</span><span class="sxs-lookup"><span data-stu-id="a7fa0-105">This control mitigates the risk of malware or malicious scripts by requiring that only code signed by a customer-approved list of publishers can run.</span></span> <span data-ttu-id="a7fa0-106">このコントロールには多くのセキュリティ上の利点がありますが、主にクライアントベースの悪用からデータと id を保護することを目的としています。</span><span class="sxs-lookup"><span data-stu-id="a7fa0-106">There are many security benefits from this control, but it primarily aims to protect data and identity from client-based exploits.</span></span>

<span data-ttu-id="a7fa0-107">Microsoft マネージドデスクトップは、コアとなる生産性シナリオを実現する基本ポリシーを作成することによって、アプリ制御ポリシーの管理を簡素化します。</span><span class="sxs-lookup"><span data-stu-id="a7fa0-107">Microsoft Managed Desktop simplifies the management of app control policies by creating a base policy that enables core productivity scenarios.</span></span> <span data-ttu-id="a7fa0-108">信頼を環境内のアプリやスクリプトに固有の追加の署名者に拡張することができます。</span><span class="sxs-lookup"><span data-stu-id="a7fa0-108">You can extend trust to additional signers that are specific to the apps and scripts in your environment.</span></span> 


<span data-ttu-id="a7fa0-109">セキュリティテクノロジには、ユーザーの環境、セキュリティ、コストの間でバランスを取る必要があります。</span><span class="sxs-lookup"><span data-stu-id="a7fa0-109">Any security technology requires a balance among user experience, security, and cost.</span></span> <span data-ttu-id="a7fa0-110">アプリの制御によって、環境内の悪意のあるソフトウェアの脅威が軽減されますが、エンドユーザーと IT 管理者に対する追加のアクションには影響があります。</span><span class="sxs-lookup"><span data-stu-id="a7fa0-110">App control reduces the threat of malicious software in your environment, but there are consequences to the end user and additional actions for your IT administrator.</span></span>

<span data-ttu-id="a7fa0-111">**追加のセキュリティ:**</span><span class="sxs-lookup"><span data-stu-id="a7fa0-111">**Additional security:**</span></span>

<span data-ttu-id="a7fa0-112">アプリコントロールポリシーによって信頼されていないアプリまたはスクリプトは、デバイス上での実行がブロックされます。</span><span class="sxs-lookup"><span data-stu-id="a7fa0-112">Apps or scripts that are not trusted by the app control policy are blocked from running on devices.</span></span>

<span data-ttu-id="a7fa0-113">**追加の責任:**</span><span class="sxs-lookup"><span data-stu-id="a7fa0-113">**Your additional responsibilities:**</span></span>

- <span data-ttu-id="a7fa0-114">アプリをテストして、アプリケーション制御ポリシーによってブロックされるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="a7fa0-114">You are responsible for testing your apps to identify whether they would be blocked by the application control policy.</span></span>
- <span data-ttu-id="a7fa0-115">アプリがブロックされている (またはそのようになる) 場合、必要な署名者の詳細を特定し、管理ポータルを通じて変更を要求する責任があります。</span><span class="sxs-lookup"><span data-stu-id="a7fa0-115">If an app is (or would be) blocked, you are responsible for identifying the needed signer details and requesting a change through the Admin portal.</span></span>

<span data-ttu-id="a7fa0-116">**Microsoft マネージドデスクトップの役割:**</span><span class="sxs-lookup"><span data-stu-id="a7fa0-116">**Microsoft Managed Desktop responsibilities:**</span></span>

- <span data-ttu-id="a7fa0-117">Microsoft マネージドデスクトップは、M365 アプリ、Windows、Teams、OneDrive などの主要な Microsoft 製品を有効にする基本ポリシーを維持しています。</span><span class="sxs-lookup"><span data-stu-id="a7fa0-117">Microsoft Managed Desktop maintains the base policy that enables core Microsoft products like M365 Apps, Windows, Teams, OneDrive, and so on.</span></span>
- <span data-ttu-id="a7fa0-118">Microsoft マネージドデスクトップは、信頼できる署名者を挿入し、更新されたポリシーをデバイスに展開します。</span><span class="sxs-lookup"><span data-stu-id="a7fa0-118">Microsoft Managed Desktop inserts your trusted signers and deploys the updated policy to your devices.</span></span>


## <a name="managing-trust-in-applications"></a><span data-ttu-id="a7fa0-119">アプリケーションでの信頼の管理</span><span class="sxs-lookup"><span data-stu-id="a7fa0-119">Managing trust in applications</span></span>

<span data-ttu-id="a7fa0-120">Microsoft マネージドデスクトップは、Microsoft テクノロジのコアコンポーネントを信頼する基本ポリシーを示しています。</span><span class="sxs-lookup"><span data-stu-id="a7fa0-120">Microsoft Managed Desktop curates a base policy that trusts the core components of Microsoft technologies.</span></span> <span data-ttu-id="a7fa0-121">その後、自分のアプリケーションとスクリプトの信頼を*追加*します。これには、既に信頼していることを Microsoft マネージドデスクトップに通知します。</span><span class="sxs-lookup"><span data-stu-id="a7fa0-121">You then *add* trust for your own applications and scripts by informing Microsoft Managed Desktop which of them you already trust.</span></span>

### <a name="base-policy"></a><span data-ttu-id="a7fa0-122">基本ポリシー</span><span class="sxs-lookup"><span data-stu-id="a7fa0-122">Base policy</span></span>

<span data-ttu-id="a7fa0-123">Microsoft マネージドデスクトップ、microsoft cybersecurity の専門家との共同作業では、Microsoft Intune 経由で展開されるほとんどのアプリを有効にする標準ポリシーを作成して管理し、コードのコンパイルや信頼されていないファイルの実行などの危険なアクティビティをブロックします。</span><span class="sxs-lookup"><span data-stu-id="a7fa0-123">Microsoft Managed Desktop, in collaboration with Microsoft cybersecurity experts, creates and maintains a standard policy that enables most apps deployed through Microsoft Intune while blocking dangerous activities like code compilation or execution of untrusted files.</span></span>

<span data-ttu-id="a7fa0-124">ソフトウェアの実行を制限するために、基本ポリシーには次の方法があります。</span><span class="sxs-lookup"><span data-stu-id="a7fa0-124">The base policy takes the following approach to restricting software execution:</span></span>

- <span data-ttu-id="a7fa0-125">管理者によって実行されるファイルは、実行が許可されます。</span><span class="sxs-lookup"><span data-stu-id="a7fa0-125">Files run by administrators will be allowed to run.</span></span>
- <span data-ttu-id="a7fa0-126">ユーザー書き込み可能なディレクトリに*ない*場所にあるファイルは、実行を許可されます。</span><span class="sxs-lookup"><span data-stu-id="a7fa0-126">Files in locations that are *not* in user-writable directories will be allowed to run.</span></span>
- <span data-ttu-id="a7fa0-127">ファイルは、[信頼できる署名者](#signer-requests)によって署名されます。</span><span class="sxs-lookup"><span data-stu-id="a7fa0-127">Files are signed by a [trusted signer](#signer-requests).</span></span>
- <span data-ttu-id="a7fa0-128">Microsoft によって署名されるほとんどのファイルは実行されますが、コードのコンパイルのような高リスクのアクションを阻止するためブロックされます。</span><span class="sxs-lookup"><span data-stu-id="a7fa0-128">Most files signed by Microsoft will run, however some are blocked to prevent high-risk actions like code compilation.</span></span>


<span data-ttu-id="a7fa0-129">管理者以外のユーザーがアプリケーションまたはスクリプトをデバイスに追加した場合 (つまり、ユーザーが書き込み可能なディレクトリにある)、そのユーザーが管理者によって明示的に許可されていない限り、実行を許可しません。</span><span class="sxs-lookup"><span data-stu-id="a7fa0-129">If a user other than an administrator could have added an app or script to a device (that is, it's in a user-writable directory), we won't allow it to execute unless it has already been specifically allowed by an administrator.</span></span> <span data-ttu-id="a7fa0-130">ユーザーがマルウェアをインストールしようとしてフックされている場合、アプリの脆弱性によりマルウェアのインストールが試みられた場合、またはユーザーが故意に許可されていないアプリまたはスクリプトを実行しようとした場合、このポリシーは実行を停止します。</span><span class="sxs-lookup"><span data-stu-id="a7fa0-130">If a user is tricked into trying to install malware, if a vulnerability in an app the user runs attempts to install malware, or if a user intentionally tries to run an unauthorized app or script, our policy will stop execution.</span></span>

### <a name="signer-requests"></a><span data-ttu-id="a7fa0-131">署名者の要求</span><span class="sxs-lookup"><span data-stu-id="a7fa0-131">Signer requests</span></span>

<span data-ttu-id="a7fa0-132">*署名者の要求*を提出することによって、信頼するソフトウェアベンダーが提供するアプリについて通知します。</span><span class="sxs-lookup"><span data-stu-id="a7fa0-132">You inform us of which apps are provided by software vendors you trust by filing a *signer request*.</span></span> <span data-ttu-id="a7fa0-133">そうすることで、その信頼情報をベースラインアプリケーション制御ポリシーに追加し、その発行元の証明書で署名されているすべてのソフトウェアをデバイス上で実行できるようにします。</span><span class="sxs-lookup"><span data-stu-id="a7fa0-133">By doing so, we add that trust information into the baseline application control policy and allow any software signed with that publisher's certificate to run on your devices.</span></span>

## <a name="audit-and-enforced-policies"></a><span data-ttu-id="a7fa0-134">監査および適用されるポリシー</span><span class="sxs-lookup"><span data-stu-id="a7fa0-134">Audit and Enforced policies</span></span>

<span data-ttu-id="a7fa0-135">Microsoft マネージドデスクトップでは、次の2つの Microsoft Intune ポリシーを使用してアプリコントロールを提供します。</span><span class="sxs-lookup"><span data-stu-id="a7fa0-135">Microsoft Managed Desktop uses two Microsoft Intune policies to provide app control:</span></span>

### <a name="audit-policy"></a><span data-ttu-id="a7fa0-136">監査ポリシー</span><span class="sxs-lookup"><span data-stu-id="a7fa0-136">Audit policy</span></span>
<span data-ttu-id="a7fa0-137">このポリシーでは、アプリまたはスクリプトが強制されたポリシーによってブロックされるかどうかを記録するログを作成します。</span><span class="sxs-lookup"><span data-stu-id="a7fa0-137">This policy creates logs to record whether an app or script would be blocked by the Enforced policy.</span></span> <span data-ttu-id="a7fa0-138">監査ポリシーでは、アプリ制御ルールは適用されず、アプリケーションが発行元を除外する必要があるかどうかを特定するためのテストを目的としています。</span><span class="sxs-lookup"><span data-stu-id="a7fa0-138">Audit policies don't enforce app control rules and are meant for testing purposes to identify whether an application will require a publisher exemption.</span></span> <span data-ttu-id="a7fa0-139">このメソッドは、指定されたアプリまたはスクリプトの実行またはインストールをブロックするのではなく、イベントビューアーに警告 (8003 または8006イベント) を記録します。</span><span class="sxs-lookup"><span data-stu-id="a7fa0-139">It logs warnings (8003 or 8006 events) in Event Viewer instead of blocking the execution or installation of specified apps or script.</span></span>

### <a name="enforced-policy"></a><span data-ttu-id="a7fa0-140">適用されるポリシー</span><span class="sxs-lookup"><span data-stu-id="a7fa0-140">Enforced policy</span></span>
<span data-ttu-id="a7fa0-141">このポリシーでは、信頼されていないアプリとスクリプトの実行をブロックし、アプリまたはスクリプトがブロックされるたびにログを作成します。</span><span class="sxs-lookup"><span data-stu-id="a7fa0-141">This policy blocks untrusted apps and scripts from running and creates logs whenever an app or script is blocked.</span></span> <span data-ttu-id="a7fa0-142">ポリシーを適用すると、ユーザーが書き込み可能なディレクトリに格納されているアプリやスクリプトを標準ユーザーが実行できなくなります。</span><span class="sxs-lookup"><span data-stu-id="a7fa0-142">Enforced policies prevent standard users from executing apps or scripts stored in user-writable directories.</span></span>

<span data-ttu-id="a7fa0-143">テストグループ内のデバイスには監査ポリシーが適用されているため、これを使用してアプリケーションが問題を引き起こすかどうかを検証できます。</span><span class="sxs-lookup"><span data-stu-id="a7fa0-143">Devices in the Test group have an Audit policy applied so that you can use them to validate whether any applications will cause issues.</span></span> <span data-ttu-id="a7fa0-144">他のすべてのグループ (ファースト、Fast、および広範) は、強制されたポリシーを使用するため、これらのグループのエンドユーザーは信頼されていないアプリやスクリプトを実行することはできません。</span><span class="sxs-lookup"><span data-stu-id="a7fa0-144">All other groups (First, Fast, and Broad) use an Enforced policy, so end users in those groups won't be able to run untrusted apps or scripts.</span></span>







