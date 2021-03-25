---
title: 証明書に基づいてインジケーターを作成する
ms.reviewer: ''
description: エンティティの検出、防止、除外を定義する証明書に基づいてインジケーターを作成します。
keywords: ioc、証明書、証明書、管理、許可、ブロック、ブロック、クリーン、悪意のある、ファイル ハッシュ、IP アドレス、URL、ドメイン
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 8cf611e38bc781c2302f70f6491bb827410235b0
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51164683"
---
# <a name="create-indicators-based-on-certificates"></a><span data-ttu-id="6d411-104">証明書に基づいてインジケーターを作成する</span><span class="sxs-lookup"><span data-stu-id="6d411-104">Create indicators based on certificates</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="6d411-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="6d411-105">**Applies to:**</span></span>
- [<span data-ttu-id="6d411-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="6d411-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="6d411-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6d411-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="6d411-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="6d411-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="6d411-109">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="6d411-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)

<span data-ttu-id="6d411-110">証明書のインジケーターを作成できます。</span><span class="sxs-lookup"><span data-stu-id="6d411-110">You can create indicators for certificates.</span></span> <span data-ttu-id="6d411-111">一般的な使用例には、次のようなものがあります。</span><span class="sxs-lookup"><span data-stu-id="6d411-111">Some common use cases include:</span></span>

- <span data-ttu-id="6d411-112">攻撃表面の縮小ルールやフォルダー アクセスの制御[](attack-surface-reduction.md)など、ブロック テクノロジ[](controlled-folders.md)を展開する必要があるが、許可リストに証明書を追加して署名済みアプリケーションからの動作を許可する必要があるシナリオ。</span><span class="sxs-lookup"><span data-stu-id="6d411-112">Scenarios when you need to deploy blocking technologies, such as [attack surface reduction rules](attack-surface-reduction.md) and [controlled folder access](controlled-folders.md) but need to allow behaviors from signed applications by adding the certificate in the allow list.</span></span>
- <span data-ttu-id="6d411-113">組織全体で特定の署名付きアプリケーションの使用をブロックする。</span><span class="sxs-lookup"><span data-stu-id="6d411-113">Blocking the use of a specific signed application across your organization.</span></span> <span data-ttu-id="6d411-114">アプリケーションの証明書をブロックするインジケーターを作成すると、Windows Defender AV はファイルの実行 (ブロックと修復) を防止し、自動調査と修復は同じように動作します。</span><span class="sxs-lookup"><span data-stu-id="6d411-114">By creating an indicator to block the certificate of the application, Windows Defender AV will prevent file executions (block and remediate) and the Automated Investigation and Remediation behave the same.</span></span>


### <a name="before-you-begin"></a><span data-ttu-id="6d411-115">はじめに</span><span class="sxs-lookup"><span data-stu-id="6d411-115">Before you begin</span></span>

<span data-ttu-id="6d411-116">証明書のインジケーターを作成する前に、次の要件を理解することが重要です。</span><span class="sxs-lookup"><span data-stu-id="6d411-116">It's important to understand the following requirements prior to creating indicators for certificates:</span></span>

- <span data-ttu-id="6d411-117">この機能は、組織でウイルス対策とクラウドベースWindows Defenderが有効になっている場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="6d411-117">This feature is available if your organization uses Windows Defender Antivirus and Cloud-based protection is enabled.</span></span> <span data-ttu-id="6d411-118">詳細については、「クラウドベースの保護 [を管理する」を参照してください](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus)。</span><span class="sxs-lookup"><span data-stu-id="6d411-118">For more information, see [Manage cloud-based protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus).</span></span>
- <span data-ttu-id="6d411-119">マルウェア対策クライアントのバージョンは、4.18.1901.x 以降である必要があります。</span><span class="sxs-lookup"><span data-stu-id="6d411-119">The Antimalware client version must be  4.18.1901.x or later.</span></span>
- <span data-ttu-id="6d411-120">Windows 10 バージョン 1703 以降の Windows Server 2016 および 2019 のコンピューターでサポートされます。</span><span class="sxs-lookup"><span data-stu-id="6d411-120">Supported on machines on Windows 10, version 1703 or later, Windows server 2016 and 2019.</span></span>
- <span data-ttu-id="6d411-121">ウイルスおよび脅威保護の定義は最新である必要があります。</span><span class="sxs-lookup"><span data-stu-id="6d411-121">The virus and threat protection definitions must be up to date.</span></span>
- <span data-ttu-id="6d411-122">この機能は現在、 の入力をサポートしています。CER または .PEM ファイル拡張子。</span><span class="sxs-lookup"><span data-stu-id="6d411-122">This feature currently supports entering .CER or .PEM file extensions.</span></span>

>[!IMPORTANT]
> - <span data-ttu-id="6d411-123">有効なリーフ証明書は、有効な証明書パスを持ち、Microsoft が信頼するルート証明機関 (CA) にチェーンする必要がある署名証明書です。</span><span class="sxs-lookup"><span data-stu-id="6d411-123">A valid leaf certificate is a signing certificate that has a valid certification path and must be chained to the Root Certificate Authority (CA) trusted by Microsoft.</span></span>  <span data-ttu-id="6d411-124">または、カスタム (自己署名証明書) 証明書は、クライアントによって信頼されている限り使用できます (ルート CA 証明書は、ローカル コンピューターの [信頼されたルート証明機関] の下にインストールされます)。</span><span class="sxs-lookup"><span data-stu-id="6d411-124">Alternatively, a custom (self-signed) certificate can be used as long as it's trusted by the client (Root CA certificate is installed under the Local Machine 'Trusted Root Certification Authorities').</span></span>
>- <span data-ttu-id="6d411-125">許可/ブロック証明書 IOC の子または親は、許可/ブロック IoC 機能には含まれません。リーフ証明書だけがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="6d411-125">The children or parent of the allow/block certificate IOCs are not included in the allow/block IoC functionality, only leaf certificates are supported.</span></span>
>- <span data-ttu-id="6d411-126">Microsoft 署名された証明書はブロックできません。</span><span class="sxs-lookup"><span data-stu-id="6d411-126">Microsoft signed certificates cannot be blocked.</span></span>

#### <a name="create-an-indicator-for-certificates-from-the-settings-page"></a><span data-ttu-id="6d411-127">設定ページから証明書のインジケーターを作成します。</span><span class="sxs-lookup"><span data-stu-id="6d411-127">Create an indicator for certificates from the settings page:</span></span>

>[!IMPORTANT]
> <span data-ttu-id="6d411-128">証明書 IoC を作成および削除するには、最大 3 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="6d411-128">It can take up to 3 hours to create and remove a certificate IoC.</span></span>

1. <span data-ttu-id="6d411-129">ナビゲーション ウィンドウで、[設定インジケーター]**を**  >  **選択します**。</span><span class="sxs-lookup"><span data-stu-id="6d411-129">In the navigation pane, select **Settings** > **Indicators**.</span></span>  

2. <span data-ttu-id="6d411-130">[証明書] **タブを選択** します。</span><span class="sxs-lookup"><span data-stu-id="6d411-130">Select the **Certificate** tab.</span></span>

3. <span data-ttu-id="6d411-131">[インジケーター **の追加] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="6d411-131">Select **Add indicator**.</span></span>

4. <span data-ttu-id="6d411-132">次の詳細を指定します。</span><span class="sxs-lookup"><span data-stu-id="6d411-132">Specify the following details:</span></span>
   - <span data-ttu-id="6d411-133">Indicator - エンティティの詳細を指定し、インジケーターの有効期限を定義します。</span><span class="sxs-lookup"><span data-stu-id="6d411-133">Indicator - Specify the entity details and define the expiration of the indicator.</span></span>
   - <span data-ttu-id="6d411-134">Action - 実行するアクションを指定し、説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="6d411-134">Action - Specify the action to be taken and provide a description.</span></span>
   - <span data-ttu-id="6d411-135">Scope - コンピューター グループのスコープを定義します。</span><span class="sxs-lookup"><span data-stu-id="6d411-135">Scope - Define the scope of the machine group.</span></span>

5. <span data-ttu-id="6d411-136">[概要] タブで詳細を確認し、[保存] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="6d411-136">Review the details in the Summary tab, then click **Save**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="6d411-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="6d411-137">Related topics</span></span>
- [<span data-ttu-id="6d411-138">インジケーターの作成</span><span class="sxs-lookup"><span data-stu-id="6d411-138">Create indicators</span></span>](manage-indicators.md)
- [<span data-ttu-id="6d411-139">ファイルのインジケーターを作成する</span><span class="sxs-lookup"><span data-stu-id="6d411-139">Create indicators for files</span></span>](indicator-file.md)
- [<span data-ttu-id="6d411-140">IPs と URL/ドメインのインジケーターを作成する</span><span class="sxs-lookup"><span data-stu-id="6d411-140">Create indicators for IPs and URLs/domains</span></span>](indicator-ip-domain.md)
- [<span data-ttu-id="6d411-141">インジケーターの管理</span><span class="sxs-lookup"><span data-stu-id="6d411-141">Manage indicators</span></span>](indicator-manage.md)