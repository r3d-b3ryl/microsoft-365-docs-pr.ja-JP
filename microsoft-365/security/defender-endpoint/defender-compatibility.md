---
title: Defender for Endpoint とのウイルス対策ソリューションの互換性
description: Microsoft Defender for Endpoint Windows Defender動作する方法と、サードパーティのマルウェア対策クライアントを使用する場合の機能について説明します。
keywords: Windows Defender の互換性、Defender、Microsoft Defender for Endpoint、Defender for endpoint、ウイルス対策、mde
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
ms.topic: conceptual
ms.date: 05/06/2021
ms.technology: mde
ms.openlocfilehash: f5a0db755f919cb47c4cd284857ddf4e27d16996
ms.sourcegitcommit: 3b9fab82d63aea41d5f544938868c5d2cbf52d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/05/2021
ms.locfileid: "52782887"
---
# <a name="antivirus-solution-compatibility-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="8eb3c-104">Microsoft Defender for Endpoint とのウイルス対策ソリューションの互換性</span><span class="sxs-lookup"><span data-stu-id="8eb3c-104">Antivirus solution compatibility with Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="8eb3c-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="8eb3c-105">**Applies to:**</span></span>
- [<span data-ttu-id="8eb3c-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="8eb3c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="8eb3c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8eb3c-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="8eb3c-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="8eb3c-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="8eb3c-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="8eb3c-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-defendercompat-abovefoldlink)

<span data-ttu-id="8eb3c-110">Microsoft Defender for Endpoint エージェントは、ファイルMicrosoft Defender ウイルス対策機能の種類によって異なります。</span><span class="sxs-lookup"><span data-stu-id="8eb3c-110">The Microsoft Defender for Endpoint agent depends on Microsoft Defender Antivirus for some capabilities such as file scanning.</span></span>

>[!IMPORTANT]
><span data-ttu-id="8eb3c-111">エンドポイントの Defender は、[除外] のMicrosoft Defender ウイルス対策に従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="8eb3c-111">Defender for Endpoint does not adhere to the Microsoft Defender Antivirus Exclusions settings.</span></span> 

<span data-ttu-id="8eb3c-112">Defender for Endpoint デバイスでセキュリティ インテリジェンスの更新プログラムを構成する必要があります。Microsoft Defender ウイルス対策がアクティブなマルウェア対策であるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="8eb3c-112">You must configure Security intelligence updates on the Defender for Endpoint devices whether Microsoft Defender Antivirus is the active antimalware or not.</span></span> <span data-ttu-id="8eb3c-113">詳細については、「更新プログラムの[管理と基準Microsoft Defender ウイルス対策適用する」を参照してください](manage-updates-baselines-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="8eb3c-113">For more information, see [Manage Microsoft Defender Antivirus updates and apply baselines](manage-updates-baselines-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="8eb3c-114">オンボードデバイスがサードパーティのマルウェア対策クライアントによって保護されている場合、そのエンドポイントのMicrosoft Defender ウイルス対策はパッシブ モードになります。</span><span class="sxs-lookup"><span data-stu-id="8eb3c-114">If an onboarded device is protected by a third-party antimalware client, Microsoft Defender Antivirus on that endpoint will enter into passive mode.</span></span>

<span data-ttu-id="8eb3c-115">Microsoft Defender ウイルス対策は更新プログラムを受信し続け *、mspeng.exe* プロセスは実行中のサービスとして表示されますが、スキャンは実行されません。実行中のサードパーティのマルウェア対策クライアントは置き換えされません。</span><span class="sxs-lookup"><span data-stu-id="8eb3c-115">Microsoft Defender Antivirus will continue to receive updates, and the *mspeng.exe* process will be listed as a running a service, but it will not perform scans and will not replace the running third-party antimalware client.</span></span>

<span data-ttu-id="8eb3c-116">インターフェイスMicrosoft Defender ウイルス対策無効になり、デバイス上のユーザーはオンデマンド スキャンを実行したり、ほとんどのオプションを構成したりするために Microsoft Defender ウイルス対策を使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="8eb3c-116">The Microsoft Defender Antivirus interface will be disabled, and users on the device will not be able to use Microsoft Defender Antivirus to perform on-demand scans or configure most options.</span></span>

<span data-ttu-id="8eb3c-117">詳細については、「エンドポイントの互換性」Microsoft Defender ウイルス対策[Defender のトピックを参照してください](microsoft-defender-antivirus-compatibility.md)。</span><span class="sxs-lookup"><span data-stu-id="8eb3c-117">For more information, see the [Microsoft Defender Antivirus and Defender for Endpoint compatibility topic](microsoft-defender-antivirus-compatibility.md).</span></span>
