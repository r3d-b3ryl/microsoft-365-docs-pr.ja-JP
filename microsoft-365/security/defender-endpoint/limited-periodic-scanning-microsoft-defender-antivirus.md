---
title: 制限された定期的なスキャン機能Microsoft Defender ウイルス対策有効にする
description: 定期的なスキャンが制限されている場合は、インストールMicrosoft Defender ウイルス対策 AV プロバイダーに加えて、定期的なスキャンを使用できます。
keywords: lps、制限付き、定期的、スキャン、スキャン、互換性、サードパーティ、その他の AV、無効化
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: ad49b08e687f4ba389616542bd607d4140e91132
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926693"
---
# <a name="use-limited-periodic-scanning-in-microsoft-defender-antivirus"></a><span data-ttu-id="047c5-104">Microsoft Defender ウイルス対策で限定された定期的なスキャンを使用する</span><span class="sxs-lookup"><span data-stu-id="047c5-104">Use limited periodic scanning in Microsoft Defender Antivirus</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="047c5-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="047c5-105">**Applies to:**</span></span>

- [<span data-ttu-id="047c5-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="047c5-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="047c5-107">限定的な定期的なスキャンは、特定のデバイスに別のウイルス対策製品をインストールした場合に有効にできる、特別な種類の脅威の検出と修復Windows 10です。</span><span class="sxs-lookup"><span data-stu-id="047c5-107">Limited periodic scanning is a special type of threat detection and remediation that can be enabled when you have installed another antivirus product on a Windows 10 device.</span></span>

<span data-ttu-id="047c5-108">特定の状況でのみ有効にできます。</span><span class="sxs-lookup"><span data-stu-id="047c5-108">It can only be enabled in certain situations.</span></span> <span data-ttu-id="047c5-109">制限付き定期的なスキャンと他のウイルス対策Microsoft Defender ウイルス対策の動作の詳細については、「Microsoft Defender ウイルス対策[を参照してください](microsoft-defender-antivirus-compatibility.md)。</span><span class="sxs-lookup"><span data-stu-id="047c5-109">For more information about limited periodic scanning and how Microsoft Defender Antivirus works with other antivirus products, see [Microsoft Defender Antivirus compatibility](microsoft-defender-antivirus-compatibility.md).</span></span>

<span data-ttu-id="047c5-110">**Microsoft では、この機能をエンタープライズ環境で使用することをお勧めしません。これは主にコンシューマー向け機能です。**</span><span class="sxs-lookup"><span data-stu-id="047c5-110">**Microsoft does not recommend using this feature in enterprise environments. This is a feature primarily intended for consumers.**</span></span> <span data-ttu-id="047c5-111">この機能は、マルウェアを検出するためにMicrosoft Defender ウイルス対策機能の限られたサブセットのみを使用し、ほとんどのマルウェアや望ましくない可能性のあるソフトウェアを検出することは可能ではありません。</span><span class="sxs-lookup"><span data-stu-id="047c5-111">This feature only uses a limited subset of the Microsoft Defender Antivirus capabilities to detect malware, and will not be able to detect most malware and potentially unwanted software.</span></span> <span data-ttu-id="047c5-112">また、管理およびレポート機能は制限されます。</span><span class="sxs-lookup"><span data-stu-id="047c5-112">Also, management and reporting capabilities will be limited.</span></span> <span data-ttu-id="047c5-113">Microsoft では、企業がプライマリ ウイルス対策ソリューションを選択し、排他的に使用する方法をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="047c5-113">Microsoft recommends enterprises choose their primary antivirus solution and use it exclusively.</span></span>

## <a name="how-to-enable-limited-periodic-scanning"></a><span data-ttu-id="047c5-114">制限付き定期的なスキャンを有効にする方法</span><span class="sxs-lookup"><span data-stu-id="047c5-114">How to enable limited periodic scanning</span></span>

<span data-ttu-id="047c5-115">既定では、Microsoft Defender ウイルス対策 は、他のウイルス対策製品がインストールされていない場合、または他の製品が期限切れ、期限切れ、または正しく動作していない場合、Windows 10 デバイス上でそれ自体を有効にします。</span><span class="sxs-lookup"><span data-stu-id="047c5-115">By default, Microsoft Defender Antivirus will enable itself on a Windows 10 device if there is no other antivirus product installed, or if the other product is out-of-date, expired, or not working correctly.</span></span>

<span data-ttu-id="047c5-116">有効Microsoft Defender ウイルス対策場合、通常のオプションが表示され、そのデバイスで構成されます。</span><span class="sxs-lookup"><span data-stu-id="047c5-116">If Microsoft Defender Antivirus is enabled, the usual options will appear to configure it on that device:</span></span>

![Windows セキュリティオプション、設定、更新オプションなど、Microsoft Defender AV オプションを表示するアプリ](images/vtp-wdav.png)

<span data-ttu-id="047c5-118">別のウイルス対策製品がインストールされ、正しく動作している場合、Microsoft Defender ウイルス対策が無効になります。</span><span class="sxs-lookup"><span data-stu-id="047c5-118">If another antivirus product is installed and working correctly, Microsoft Defender Antivirus will disable itself.</span></span> <span data-ttu-id="047c5-119">アプリWindows セキュリティ[ウイルス対策&] セクションが変更され、AV 製品に関する状態が表示され、製品の構成オプションへのリンクが提供されます。</span><span class="sxs-lookup"><span data-stu-id="047c5-119">The Windows Security app will change the **Virus & threat protection** section to show status about the AV product, and provide a link to the product's configuration options.</span></span>

<span data-ttu-id="047c5-120">サード パーティの AV 製品の下に、新しいリンクが新しいオプション **としてMicrosoft Defender ウイルス対策されます**。</span><span class="sxs-lookup"><span data-stu-id="047c5-120">Underneath any third party AV products, a new link will appear as **Microsoft Defender Antivirus options**.</span></span> <span data-ttu-id="047c5-121">このリンクをクリックすると、制限付き定期的なスキャンを有効にするトグルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="047c5-121">Clicking this link will expand to show the toggle that enables limited periodic scanning.</span></span> <span data-ttu-id="047c5-122">制限された定期的なオプションは、定期的なスキャンを有効または無効にするトグルです。</span><span class="sxs-lookup"><span data-stu-id="047c5-122">Note that the limited periodic option is a toggle to enable or disable periodic scanning.</span></span> 

<span data-ttu-id="047c5-123">スイッチを On に **スライドすると** 、サードパーティの AV 製品の下に標準の Microsoft Defender AV オプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="047c5-123">Sliding the switch to **On** will show the standard Microsoft Defender AV options underneath the third party AV product.</span></span> <span data-ttu-id="047c5-124">制限された定期的なスキャン オプションがページの下部に表示されます。</span><span class="sxs-lookup"><span data-stu-id="047c5-124">The limited periodic scanning option will appear at the bottom of the page.</span></span>

## <a name="related-articles"></a><span data-ttu-id="047c5-125">関連資料</span><span class="sxs-lookup"><span data-stu-id="047c5-125">Related articles</span></span>

- [<span data-ttu-id="047c5-126">行動、ヒューリスティック、リアルタイム保護を構成する</span><span class="sxs-lookup"><span data-stu-id="047c5-126">Configure behavioral, heuristic, and real-time protection</span></span>](configure-protection-features-microsoft-defender-antivirus.md)
- [<span data-ttu-id="047c5-127">Microsoft Defender ウイルス対策 (Windows 10)</span><span class="sxs-lookup"><span data-stu-id="047c5-127">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)