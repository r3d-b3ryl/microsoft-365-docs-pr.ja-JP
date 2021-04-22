---
title: Microsoft Defender ウイルス対策と Defender for Endpoint の互換性
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
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: a8dca4a80385fabcdc64a5584474214d05be4a6c
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935379"
---
# <a name="microsoft-defender-antivirus-compatibility-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="794c5-104">Microsoft Defender ウイルス対策と Microsoft Defender for Endpoint の互換性</span><span class="sxs-lookup"><span data-stu-id="794c5-104">Microsoft Defender Antivirus compatibility with Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="794c5-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="794c5-105">**Applies to:**</span></span>
- [<span data-ttu-id="794c5-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="794c5-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="794c5-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="794c5-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="794c5-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="794c5-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="794c5-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="794c5-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-defendercompat-abovefoldlink)

<span data-ttu-id="794c5-110">Microsoft Defender for Endpoint エージェントは、ファイルスキャンなどの一部の機能について Microsoft Defender ウイルス対策に依存します。</span><span class="sxs-lookup"><span data-stu-id="794c5-110">The Microsoft Defender for Endpoint agent depends on Microsoft Defender Antivirus for some capabilities such as file scanning.</span></span>

>[!IMPORTANT]
><span data-ttu-id="794c5-111">エンドポイントの Defender は、Microsoft Defender ウイルス対策の除外設定に従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="794c5-111">Defender for Endpoint does not adhere to the Microsoft Defender Antivirus Exclusions settings.</span></span> 

<span data-ttu-id="794c5-112">Microsoft Defender ウイルス対策がアクティブなマルウェア対策かどうかに関して、Defender for Endpoint デバイスでセキュリティ インテリジェンス更新プログラムを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="794c5-112">You must configure Security intelligence updates on the Defender for Endpoint devices whether Microsoft Defender Antivirus is the active antimalware or not.</span></span> <span data-ttu-id="794c5-113">詳細については [、「Manage Microsoft Defender Antivirus updates and apply baselines」を参照してください](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="794c5-113">For more information, see [Manage Microsoft Defender Antivirus updates and apply baselines](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="794c5-114">オンボードデバイスがサードパーティのマルウェア対策クライアントによって保護されている場合、そのエンドポイントの Microsoft Defender Antivirus はパッシブ モードになります。</span><span class="sxs-lookup"><span data-stu-id="794c5-114">If an onboarded device is protected by a third-party antimalware client, Microsoft Defender Antivirus on that endpoint will enter into passive mode.</span></span>

<span data-ttu-id="794c5-115">Microsoft Defender ウイルス対策は引き続き更新プログラムを受け取り *、mspeng.exe* プロセスは実行中のサービスとして表示されますが、スキャンは実行されません。実行中のサードパーティのマルウェア対策クライアントは置き換えされません。</span><span class="sxs-lookup"><span data-stu-id="794c5-115">Microsoft Defender Antivirus will continue to receive updates, and the *mspeng.exe* process will be listed as a running a service, but it will not perform scans and will not replace the running third-party antimalware client.</span></span>

<span data-ttu-id="794c5-116">Microsoft Defender ウイルス対策インターフェイスは無効になり、デバイス上のユーザーは Microsoft Defender ウイルス対策を使用してオンデマンド スキャンを実行したり、ほとんどのオプションを構成したりできなくなります。</span><span class="sxs-lookup"><span data-stu-id="794c5-116">The Microsoft Defender Antivirus interface will be disabled, and users on the device will not be able to use Microsoft Defender Antivirus to perform on-demand scans or configure most options.</span></span>

<span data-ttu-id="794c5-117">詳細については、「Microsoft Defender Antivirus and Defender for Endpoint の互換性」 [を参照してください](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)。</span><span class="sxs-lookup"><span data-stu-id="794c5-117">For more information, see the [Microsoft Defender Antivirus and Defender for Endpoint compatibility topic](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility).</span></span>
