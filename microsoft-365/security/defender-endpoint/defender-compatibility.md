---
title: Defender for Endpoint とのウイルス対策ソリューションの互換性
description: Microsoft Defender for EndpointとWindows Defenderのしくみについて説明します。 また、サード パーティのマルウェア対策クライアントが使用されている場合の Defender for Endpoint のしくみについても説明します。
keywords: Windows Defender の互換性, Defender, Microsoft Defender for Endpoint, エンドポイント用 Defender, ウイルス対策, mde
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.date: 05/06/2021
ms.technology: mde
ms.openlocfilehash: a8384ed28e8c65871f61241dc522461390106be0
ms.sourcegitcommit: eb8c600d3298dca1940259998de61621e6505e69
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/24/2021
ms.locfileid: "61164564"
---
# <a name="antivirus-solution-compatibility-with-microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpointとのウイルス対策ソリューションの互換性

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-defendercompat-abovefoldlink)

Microsoft Defender for Endpoint エージェントは、ファイル スキャンなどの一部の機能のMicrosoft Defender ウイルス対策に依存します。

> [!IMPORTANT]
> Defender for Endpoint は、Microsoft Defender ウイルス対策除外設定に準拠しません。

Microsoft Defender ウイルス対策がアクティブなマルウェア対策であるかどうかに関係なく、Defender for Endpoint デバイスでセキュリティ インテリジェンス更新プログラムを構成する必要があります。 詳細については、「[Microsoft Defender ウイルス対策の更新プログラムを管理してベースラインを適用する](manage-updates-baselines-microsoft-defender-antivirus.md)」を参照してください。

オンボードされたデバイスがサードパーティのマルウェア対策クライアントによって保護されている場合、そのエンドポイントのMicrosoft Defender ウイルス対策はパッシブ モードになります。

Microsoft Defender ウイルス対策は引き続き更新プログラムを受け取り、*mspeng.exe* プロセスは実行中のサービスとして一覧表示されます。 ただし、スキャンは実行されません。実行中のサード パーティのマルウェア対策クライアントは置き換えられません。

Microsoft Defender ウイルス対策 インターフェイスは無効になります。 デバイス上のユーザーは、Microsoft Defender ウイルス対策を使用してオンデマンド スキャンを実行したり、ほとんどのオプションを構成したりすることはできません。

詳細については、[Microsoft Defender ウイルス対策と Defender for Endpoint の互換性に関するトピックを](microsoft-defender-antivirus-compatibility.md)参照してください。
