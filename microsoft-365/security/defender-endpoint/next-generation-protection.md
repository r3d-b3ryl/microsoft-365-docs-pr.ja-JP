---
title: Microsoft Defender for Endpoint の次世代保護の概要
description: Microsoft Defender for Endpoint の次世代保護の概要をご覧ください。 あらゆる種類の新たな脅威を捕らえるように設計された次世代保護を使用して、ネットワークのセキュリティ境界を強化します。
keywords: Microsoft Defender ウイルス対策、Windows Defender、マルウェア対策、ウイルス、マルウェア、脅威、検出、保護、セキュリティ
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: high
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.reviewer: mkaminska
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.collection: M365-security-compliance
ms.openlocfilehash: 94f920d298c5b74eff39290ced4ccdc58031ac0f
ms.sourcegitcommit: 355ab75eb7b604c6afbe9a5a1b97ef16a1dec4fc
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2022
ms.locfileid: "62807406"
---
# <a name="next-generation-protection-overview"></a>次世代保護の概要

**適用対象**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

Microsoft Defender for Endpoint には、ネットワークのセキュリティ境界を強化するための次世代保護が含まれています。 次世代保護は、あらゆる種類の新たな脅威を捕らえるように設計されました。 Microsoft Defender ウイルス対策に加えて、次世代保護サービスには以下の機能が含まれています。

- [挙動ベースおよびヒューリスティックのリアルタイム ウイルス対策保護](configure-protection-features-microsoft-defender-antivirus.md)。これには、ファイルとプロセスの動作監視およびその他のヒューリスティックを使用した常時オンのスキャンが含まれています (「*リアルタイム保護*」とも呼ばれています)。 安全ではないと見なされているもののマルウェアとして検出されない可能性のあるアプリの検出とブロックも含まれています。
- [クラウドによる保護](cloud-protection-microsoft-defender-antivirus.md)。これには、新たに出現する脅威のほぼ瞬時の検出とブロックが含まれています。
- [専用の保護および製品の更新プログラム](manage-updates-baselines-microsoft-defender-antivirus.md)。これには、Microsoft Defender ウイルス対策を最新状態に維持することに関連する更新プログラムが含まれています。

> [!TIP]
> 次世代の保護は、Microsoft Defender for Endpoint プラン 1 とプラン 2 の両方に含まれています。 [Defender for Endpoint プラン 1 とプラン 2 についての詳細](defender-endpoint-plan-1-2.md)

## <a name="try-a-demo"></a>デモを試す

[Microsoft Defender for Endpoint のデモ用 Web サイト](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground)にアクセスし、以下の保護機能が動作していることを確認したり、デモのシナリオを使用して検証したりしましょう。

- クラウドによる保護
- 事前ブロック (BAFS) 保護
- 望ましくない可能性のあるアプリケーション (PUA) 保護

> [!NOTE]
> demo.wd.microsoft.com の Defender for Endpoint デモ サイトは推奨されません。今後削除される予定です。

## <a name="configure-next-generation-protection-services"></a>次世代の保護サービスを構成する

次世代の保護サービスを構成する方法の詳細については、「[Microsoft Defender ウイルス対策機能を構成する](configure-microsoft-defender-antivirus-features.md)」を参照してください。

> [!NOTE]
> 構成と管理は、Windows Server と Windows クライアントでほぼ同じです。 ただし、いくつかの違いがあります。 
