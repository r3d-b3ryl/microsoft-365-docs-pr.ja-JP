---
title: 評価環境Microsoft 365 Defenderを Production に昇格する
description: この記事を使用して、MDI、MDO、MDE、MCAS のエバルを、Microsoft 365 Defender または M365D のライブ環境に昇格します。
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 51b03ebf277583541fc86bdbd80535704929fcf3
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59219994"
---
# <a name="promote-your-microsoft-365-defender-evaluation-environment-to-production"></a>評価環境Microsoft 365 Defenderを実稼働環境に昇格する

**適用対象:**
- Microsoft 365 Defender

評価環境をMicrosoft 365 Defenderするには、まず必要なライセンスを購入します。 「eval[環境の作成」](eval-create-eval-environment.md)の手順に従って、ライセンスOffice 365 E5購入します ([無料試用版の開始] を選択する代わりに)。

次に、追加の構成を完了し、パイロット グループが完全に稼働するまで展開します。 

## <a name="microsoft-defender-for-identity"></a>Microsoft Defender for Identity
Id の Defender は、追加の構成を必要とします。 必要なライセンスを購入し、すべての Active Directory ドメイン コントローラーと Active Directory フェデレーション サービス (AD FS) サーバーにセンサーをインストールしてください。 

## <a name="microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365
MDO を正常に評価またはパイロットした後、その MDO を実稼働環境全体に昇格できます。
1. 必要なライセンスを購入してプロビジョニングし、実稼働ユーザーに割り当てる。
2. 推奨されるベースライン ポリシー構成 (Standard または Strict) を、実稼働メール ドメインまたは特定のユーザー グループに対して再実行します。
3. 必要に応じて、実稼働メール ドメインまたはユーザー グループに対してカスタム MDO ポリシーを作成して構成します。  ただし、割り当てられた基準ポリシーは常にカスタム ポリシーよりも優先されます。
4. 運用メール ドメインのパブリック MX レコードを更新して、EOP に直接解決します。
5. サードパーティの SMTP ゲートウェイを使用停止し、このリレーに関連付けられている EXO コネクタを無効または削除します。

## <a name="microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpoint
Microsoft Defender for Endpoint 評価環境をパイロットから実稼働環境に昇格するには、サポートされているツールと方法を使用して、より多くのエンドポイントをサービスに [オンボードします](../defender-endpoint/onboard-configure.md)。

Microsoft Defender for Endpoint に追加のデバイスをオンボードするには、次の一般的なガイドラインを使用します。 

1. デバイスが最小要件を満 [たしていることを確認します](../defender-endpoint/minimum-requirements.md)。
2. デバイスに応じて、Defender for Endpoint ポータルのオンボーディング セクションに示されている構成手順に従います。
3. デバイスに適切な管理ツールと展開方法を使用します。
4.  検出テストを実行して、デバイスが適切にオンボードされ、サービスに報告されていることを確認します。

## <a name="microsoft-cloud-app-security"></a>Microsoft Cloud App Security
Microsoft Cloud App Security構成は不要です。 必要なライセンスを購入しただけ。 展開の範囲を特定のユーザー グループに設定した場合は、実稼働規模に達するまで、これらのグループの範囲を広くします。 

