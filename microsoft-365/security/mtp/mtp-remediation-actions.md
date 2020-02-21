---
title: Microsoft の脅威保護での自動調査および応答機能の修復処置
description: Microsoft Threat Protection での自動調査および対応機能の概要を説明します
keywords: 自動化、調査、警告、トリガー、アクション、修復
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: 73bb90a0537df8e6f23e4e0e50a748aebda3a487
ms.sourcegitcommit: 2f117a6fd27a097ca25afa933dd088b69d483974
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/20/2020
ms.locfileid: "42175943"
---
# <a name="remediation-actions-in-automated-investigation-and-response-capabilities-in-microsoft-threat-protection"></a>Microsoft の脅威保護での自動調査および応答機能の修復処置

**適用対象:**
- Microsoft Threat Protection

Microsoft の脅威保護の自動化された調査と応答機能には、特定の修復アクションが含まれています。 一部の種類の修復アクションは、エンドポイントとも呼ばれるデバイスで実行されます。 その他の修復アクションは、電子メールコンテンツに対して実行されます。

次の表に、Microsoft の脅威保護で現在サポートされている修復アクションの概要を示します。 

|エンドポイントの修復アクション  |メールの修復アクション  |
|---------|---------|
|ファイルの検疫<br/>レジストリ キーの削除<br/>プロセスの強制終了 <br/>サービスの停止 <br/>レジストリ キーの削除 <br/>ドライバーの無効化 <br/>スケジュールされたタスクの実行      |メール メッセージまたはクラスターの論理的な削除<br/>URL のブロック (クリック時)<br/>外部メール転送の無効化          |

修復が保留になっているか、既に完了しているかにかかわらず、[アクションセンター](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)で確認できます。

## <a name="next-steps"></a>次のステップ

- [自動調査と対応に関連するアクションを承認または拒否する](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir-actions)
- [アクション センターの詳細](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)
