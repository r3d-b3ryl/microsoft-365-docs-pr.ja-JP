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
ms.openlocfilehash: b75a8cf1d2681281555a3b7bb80deadfc11ee44c
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845453"
---
# <a name="create-indicators-based-on-certificates"></a><span data-ttu-id="3c72d-104">証明書に基づいてインジケーターを作成する</span><span class="sxs-lookup"><span data-stu-id="3c72d-104">Create indicators based on certificates</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="3c72d-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="3c72d-105">**Applies to:**</span></span>
- [<span data-ttu-id="3c72d-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="3c72d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="3c72d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3c72d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="3c72d-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="3c72d-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="3c72d-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="3c72d-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)

<span data-ttu-id="3c72d-110">証明書のインジケーターを作成できます。</span><span class="sxs-lookup"><span data-stu-id="3c72d-110">You can create indicators for certificates.</span></span> <span data-ttu-id="3c72d-111">一般的な使用例には、次のようなものがあります。</span><span class="sxs-lookup"><span data-stu-id="3c72d-111">Some common use cases include:</span></span>

- <span data-ttu-id="3c72d-112">攻撃表面の縮小ルールやフォルダー アクセスの制御[](attack-surface-reduction.md)など、ブロック テクノロジ[](controlled-folders.md)を展開する必要があるが、許可リストに証明書を追加して署名済みアプリケーションからの動作を許可する必要があるシナリオ。</span><span class="sxs-lookup"><span data-stu-id="3c72d-112">Scenarios when you need to deploy blocking technologies, such as [attack surface reduction rules](attack-surface-reduction.md) and [controlled folder access](controlled-folders.md) but need to allow behaviors from signed applications by adding the certificate in the allow list.</span></span>
- <span data-ttu-id="3c72d-113">組織全体で特定の署名付きアプリケーションの使用をブロックする。</span><span class="sxs-lookup"><span data-stu-id="3c72d-113">Blocking the use of a specific signed application across your organization.</span></span> <span data-ttu-id="3c72d-114">アプリケーションの証明書をブロックするインジケーターを作成すると、Windows Defender AV はファイルの実行 (ブロックと修復) を防止し、自動調査と修復は同じように動作します。</span><span class="sxs-lookup"><span data-stu-id="3c72d-114">By creating an indicator to block the certificate of the application, Windows Defender AV will prevent file executions (block and remediate) and the Automated Investigation and Remediation behave the same.</span></span>


### <a name="before-you-begin"></a><span data-ttu-id="3c72d-115">はじめに</span><span class="sxs-lookup"><span data-stu-id="3c72d-115">Before you begin</span></span>

<span data-ttu-id="3c72d-116">証明書のインジケーターを作成する前に、次の要件を理解することが重要です。</span><span class="sxs-lookup"><span data-stu-id="3c72d-116">It's important to understand the following requirements prior to creating indicators for certificates:</span></span>

- <span data-ttu-id="3c72d-117">この機能は、組織でクラウド ベースのWindows Defender ウイルス対策が有効になっている場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="3c72d-117">This feature is available if your organization uses Windows Defender Antivirus and Cloud-based protection is enabled.</span></span> <span data-ttu-id="3c72d-118">詳細については、「クラウドベースの保護 [を管理する」を参照してください](/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus)。</span><span class="sxs-lookup"><span data-stu-id="3c72d-118">For more information, see [Manage cloud-based protection](/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus).</span></span>
- <span data-ttu-id="3c72d-119">マルウェア対策クライアントのバージョンは、4.18.1901.x 以降である必要があります。</span><span class="sxs-lookup"><span data-stu-id="3c72d-119">The Antimalware client version must be  4.18.1901.x or later.</span></span>
- <span data-ttu-id="3c72d-120">サーバー 2016 および 2019 Windows 10バージョン 1703 以降のコンピューター Windowsサポートされています。</span><span class="sxs-lookup"><span data-stu-id="3c72d-120">Supported on machines on Windows 10, version 1703 or later, Windows server 2016 and 2019.</span></span>
- <span data-ttu-id="3c72d-121">ウイルスおよび脅威保護の定義は最新である必要があります。</span><span class="sxs-lookup"><span data-stu-id="3c72d-121">The virus and threat protection definitions must be up to date.</span></span>
- <span data-ttu-id="3c72d-122">この機能は現在、 の入力をサポートしています。CER または .PEM ファイル拡張子。</span><span class="sxs-lookup"><span data-stu-id="3c72d-122">This feature currently supports entering .CER or .PEM file extensions.</span></span>

>[!IMPORTANT]
> - <span data-ttu-id="3c72d-123">有効なリーフ証明書は、有効な証明書パスを持ち、Microsoft が信頼するルート証明機関 (CA) にチェーンする必要がある署名証明書です。</span><span class="sxs-lookup"><span data-stu-id="3c72d-123">A valid leaf certificate is a signing certificate that has a valid certification path and must be chained to the Root Certificate Authority (CA) trusted by Microsoft.</span></span>  <span data-ttu-id="3c72d-124">または、カスタム (自己署名証明書) 証明書は、クライアントによって信頼されている限り使用できます (ルート CA 証明書は、ローカル コンピューターの [信頼されたルート証明機関] の下にインストールされます)。</span><span class="sxs-lookup"><span data-stu-id="3c72d-124">Alternatively, a custom (self-signed) certificate can be used as long as it's trusted by the client (Root CA certificate is installed under the Local Machine 'Trusted Root Certification Authorities').</span></span>
>- <span data-ttu-id="3c72d-125">許可/ブロック証明書 IOC の子または親は、許可/ブロック IoC 機能には含まれません。リーフ証明書だけがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="3c72d-125">The children or parent of the allow/block certificate IOCs are not included in the allow/block IoC functionality, only leaf certificates are supported.</span></span>
>- <span data-ttu-id="3c72d-126">Microsoft 署名された証明書はブロックできません。</span><span class="sxs-lookup"><span data-stu-id="3c72d-126">Microsoft signed certificates cannot be blocked.</span></span>

#### <a name="create-an-indicator-for-certificates-from-the-settings-page"></a><span data-ttu-id="3c72d-127">設定ページから証明書のインジケーターを作成します。</span><span class="sxs-lookup"><span data-stu-id="3c72d-127">Create an indicator for certificates from the settings page:</span></span>

>[!IMPORTANT]
> <span data-ttu-id="3c72d-128">証明書 IoC を作成および削除するには、最大 3 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="3c72d-128">It can take up to 3 hours to create and remove a certificate IoC.</span></span>

1. <span data-ttu-id="3c72d-129">ナビゲーション ウィンドウで、[インジケーター]**を設定**  >  **します**。</span><span class="sxs-lookup"><span data-stu-id="3c72d-129">In the navigation pane, select **Settings** > **Indicators**.</span></span>  

2. <span data-ttu-id="3c72d-130">[証明書] **タブを選択** します。</span><span class="sxs-lookup"><span data-stu-id="3c72d-130">Select the **Certificate** tab.</span></span>

3. <span data-ttu-id="3c72d-131">[インジケーター **の追加] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="3c72d-131">Select **Add indicator**.</span></span>

4. <span data-ttu-id="3c72d-132">次の詳細を指定します。</span><span class="sxs-lookup"><span data-stu-id="3c72d-132">Specify the following details:</span></span>
   - <span data-ttu-id="3c72d-133">Indicator - エンティティの詳細を指定し、インジケーターの有効期限を定義します。</span><span class="sxs-lookup"><span data-stu-id="3c72d-133">Indicator - Specify the entity details and define the expiration of the indicator.</span></span>
   - <span data-ttu-id="3c72d-134">Action - 実行するアクションを指定し、説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="3c72d-134">Action - Specify the action to be taken and provide a description.</span></span>
   - <span data-ttu-id="3c72d-135">Scope - コンピューター グループのスコープを定義します。</span><span class="sxs-lookup"><span data-stu-id="3c72d-135">Scope - Define the scope of the machine group.</span></span>

5. <span data-ttu-id="3c72d-136">[概要] タブで詳細を確認し、[保存] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="3c72d-136">Review the details in the Summary tab, then click **Save**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="3c72d-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="3c72d-137">Related topics</span></span>
- [<span data-ttu-id="3c72d-138">インジケーターの作成</span><span class="sxs-lookup"><span data-stu-id="3c72d-138">Create indicators</span></span>](manage-indicators.md)
- [<span data-ttu-id="3c72d-139">ファイルのインジケーターを作成 </span><span class="sxs-lookup"><span data-stu-id="3c72d-139">Create indicators for files</span></span>](indicator-file.md)
- [<span data-ttu-id="3c72d-140">IP および URL/ドメインのインジケーターを作成</span><span class="sxs-lookup"><span data-stu-id="3c72d-140">Create indicators for IPs and URLs/domains</span></span>](indicator-ip-domain.md)
- [<span data-ttu-id="3c72d-141">インジケーターの管理</span><span class="sxs-lookup"><span data-stu-id="3c72d-141">Manage indicators</span></span>](indicator-manage.md)
