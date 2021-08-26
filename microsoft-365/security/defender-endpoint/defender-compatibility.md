---
title: Defender for Endpoint とのウイルス対策ソリューションの互換性
description: Microsoft Defender for Endpoint Windows Defenderの動作について説明します。 また、サード パーティ製のマルウェア対策クライアントを使用する場合の Defender for Endpoint の動作について説明します。
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
ms.openlocfilehash: 02c6ecefc5d6393508382c436a9fe82e31200b76
ms.sourcegitcommit: 6c342a956b2dbc32be33bac1a23a5038490f1b40
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58533497"
---
# <a name="antivirus-solution-compatibility-with-microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpoint とのウイルス対策ソリューションの互換性

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-defendercompat-abovefoldlink)

Microsoft Defender for Endpoint エージェントは、ファイルMicrosoft Defender ウイルス対策機能の種類によって異なります。

> [!IMPORTANT]
> エンドポイントの Defender は、[除外] のMicrosoft Defender ウイルス対策に従う必要があります。

Defender for Endpoint デバイスでセキュリティ インテリジェンス更新プログラムを構成する必要があります(Microsoft Defender ウイルス対策がアクティブなマルウェア対策かどうか)。 詳細については、「更新プログラムの[管理と基準Microsoft Defender ウイルス対策適用する」を参照してください](manage-updates-baselines-microsoft-defender-antivirus.md)。

オンボードデバイスがサードパーティのマルウェア対策クライアントによって保護されている場合、そのエンドポイントのMicrosoft Defender ウイルス対策はパッシブ モードになります。

Microsoft Defender ウイルス対策は引き続き更新プログラムを受信し、mspeng.exeプロセスは実行中のサービスとして一覧表示されます。  ただし、スキャンは実行され、実行中のサード パーティのマルウェア対策クライアントは置き換えも行わない。

インターフェイスMicrosoft Defender ウイルス対策無効になります。 デバイス上のユーザーは、オンデマンド スキャンを実行したりMicrosoft Defender ウイルス対策オプションを構成したりするために、デバイスを使用することはできません。

詳細については、「エンドポイントの互換性」Microsoft Defender ウイルス対策[Defender のトピックを参照してください](microsoft-defender-antivirus-compatibility.md)。
