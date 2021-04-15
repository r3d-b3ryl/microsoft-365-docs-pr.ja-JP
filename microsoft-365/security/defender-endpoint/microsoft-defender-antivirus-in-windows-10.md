---
title: 次世代の保護
description: Microsoft Defender Antivirus、組み込みのマルウェア対策、ウイルス対策保護を管理、構成、および使用する方法について説明します。
keywords: Microsoft Defender ウイルス対策、Windows Defender、マルウェア対策、scep、システム センター エンドポイント保護、システム センター構成マネージャー、ウイルス、マルウェア、脅威、検出、保護、セキュリティ
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: priority
author: denisebmsft
ms.author: deniseb
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.openlocfilehash: eb7e0253b3761d05d112500c0410fffa58548221
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765421"
---
# <a name="next-generation-protection"></a>次世代の保護

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

## <a name="microsoft-defender-antivirus-your-next-generation-protection"></a>Microsoft Defender ウイルス対策: 次世代の保護

Microsoft Defender Antivirus は、Microsoft Defender for Endpoint の次世代保護コンポーネントです。 この保護により、機械学習、ビッグ データ分析、詳細な脅威耐性調査、Microsoft クラウド インフラストラクチャが統合され、企業組織内のデバイスを保護できます。 次世代の保護サービスには、次の機能が含まれます。

- [動作ベース、](configure-protection-features-microsoft-defender-antivirus.md)ヒューリスティック、リアルタイムのウイルス対策保護 。これには、ファイルとプロセスの動作監視を使用した常時スキャンと、その他のヒューリスティック (リアルタイム保護とも呼 *ばれる)* が含まれます。 また、安全ではないと見なされるが、マルウェアとして検出されない可能性があるアプリの検出とブロックも含まれます。
- [クラウドによって提供される保護](cloud-protection-microsoft-defender-antivirus.md)。これには、新しい脅威や新しい脅威のほぼ瞬時の検出とブロックが含まれます。
- [専用の保護と製品の更新](manage-updates-baselines-microsoft-defender-antivirus.md)プログラム (Microsoft Defender ウイルス対策を最新の状態に保つことに関連する更新プログラムを含む)。

## <a name="try-a-demo"></a>デモをお試しください。

Microsoft [Defender for Endpoint のデモ Web サイトにアクセス](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) して、次の保護機能が機能しているのを確認し、デモ シナリオを使用してそれらを確認します。
- クラウドによる保護
- 一目でブロックする (BAFS) 保護
- 望ましくない可能性のあるアプリケーション (PUA) 保護

## <a name="minimum-system-requirements"></a>最小システム要件

Microsoft Defender ウイルス対策には、Windows 10 と同じハードウェア要件があります。 詳細については、以下の資料を参照してください。

- [ハードウェアの最小要件](/windows-hardware/design/minimum/minimum-hardware-requirements-overview)
- [ハードウェア コンポーネントのガイドライン](/windows-hardware/design/component-guidelines/components)

## <a name="configure-next-generation-protection-services"></a>次世代保護サービスの構成

次世代保護サービスを構成する方法の詳細については [、「Configure Microsoft Defender Antivirus features」を参照してください](configure-microsoft-defender-antivirus-features.md)。

> [!Note]  
> 構成と管理は、Microsoft Defender ウイルス対策を実行している間、Windows Server 2016 と Windows Server 2019 で大きく同じです。ただし、いくつかの違いがあります。 詳細については [、「Microsoft Defender Antivirus on Windows Server 2016 and 2019」を参照してください](microsoft-defender-antivirus-on-windows-server.md)。

## <a name="see-also"></a>関連項目

- [Windows Server 2016 および 2019 の Microsoft Defender ウイルス対策](microsoft-defender-antivirus-on-windows-server.md)
- [Microsoft Defender ウイルス対策の管理と構成](configuration-management-reference-microsoft-defender-antivirus.md)
- [Microsoft Defender ウイルス対策の保護を評価する](evaluate-microsoft-defender-antivirus.md)