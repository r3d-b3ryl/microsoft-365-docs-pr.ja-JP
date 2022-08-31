---
title: 手順 7. Microsoft 365 Defender評価環境を運用環境に昇格させる
description: この記事を使用して、MDI、MDO、MDE、Defender for Cloud Apps のエベルを、Microsoft 365 Defenderまたは M365D のライブ環境に昇格させます。
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.subservice: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
- zerotrust-solution
- highpri
ms.topic: conceptual
ms.openlocfilehash: 018b8047ecce5dd4d41becb19ed779025715fe70
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2022
ms.locfileid: "67479668"
---
# <a name="step-7-promote-your-microsoft-365-defender-evaluation-environment-to-production"></a>手順 7. Microsoft 365 Defender評価環境を運用環境に昇格させる

**適用対象:**
- Microsoft 365 Defender

Microsoft 365 Defender評価環境を運用環境に昇格するには、まず必要なライセンスを購入します。 [eval 環境を作成](eval-create-eval-environment.md)し、Office 365 E5 ライセンスを購入する ([無料試用版の開始] を選択する代わりに) の手順に従います。

次に、追加の構成を完了し、パイロット グループが完全な運用に達するまで展開します。

## <a name="microsoft-defender-for-identity"></a>Microsoft Defender for Identity

Defender for Identity では、追加の構成は必要ありません。 必要なライセンスを購入し、すべての Active Directory ドメイン コントローラーと Active Directory フェデレーション サービス (AD FS) (AD FS) サーバーにセンサーをインストールしたことを確認してください。

## <a name="microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365

MDO を正常に評価またはパイロットした後は、運用環境全体に昇格できます。

1. 必要なライセンスを購入してプロビジョニングし、運用ユーザーに割り当てます。
2. 運用環境の電子メール ドメインまたは特定のユーザー グループに対して推奨されるベースライン ポリシー構成 (Standard または Strict) を再実行します。
3. 必要に応じて、運用環境の電子メール ドメインまたはユーザー のグループに対してカスタム MDO ポリシーを作成して構成します。  ただし、割り当てられたベースライン ポリシーは常にカスタム ポリシーよりも優先されることに注意してください。
4. 運用電子メール ドメインのパブリック MX レコードを更新して、EOP に直接解決します。
5. サードパーティの SMTP ゲートウェイを使用停止し、このリレーに関連付けられている EXO コネクタを無効または削除します。

## <a name="microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpoint

Microsoft Defender for Endpoint評価環境をパイロットから運用環境に昇格するには、[サポートされているツールと方法](../defender-endpoint/onboard-configure.md)のいずれかを使用して、より多くのエンドポイントをサービスにオンボードするだけです。

その他のデバイスをMicrosoft Defender for Endpointにオンボードするには、次の一般的なガイドラインを使用します。

1. デバイスが [最小要件](../defender-endpoint/minimum-requirements.md)を満たしていることを確認します。
2. デバイスに応じて、Defender for Endpoint ポータルのオンボード セクションで示されている構成手順に従います。
3. デバイスに適した管理ツールと展開方法を使用します。
4. 検出テストを実行して、デバイスが適切にオンボードされ、サービスに報告されていることを確認します。

## <a name="microsoft-defender-for-cloud-apps"></a>Microsoft Defender for Cloud Apps

Microsoft Defender for Cloud Apps追加の構成は必要ありません。 必要なライセンスを購入したことを確認してください。 デプロイの範囲を特定のユーザー グループに設定した場合は、運用スケールに達するまでこれらのグループの範囲を増やします。
