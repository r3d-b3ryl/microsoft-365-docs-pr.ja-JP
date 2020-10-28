---
title: Microsoft のセキュリティで保護されたスコア
description: Microsoft 365 セキュリティセンターで Microsoft セキュリティスコアに追加された新しい変更内容について説明します。
keywords: microsoft secure score、secure score、office 365 のセキュリティスコア、microsoft セキュリティスコア、microsoft 365 セキュリティセンター、改善アクション
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 82ec67cae86525c055b2232667cccb603830d15f
ms.sourcegitcommit: c51de5e1a4cb9c4a7a9854a4226b32453d9e73e0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/28/2020
ms.locfileid: "48779250"
---
# <a name="whats-coming-to-microsoft-secure-score"></a>Microsoft のセキュリティで保護されたスコア

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

弊社では、セキュリティ上の姿勢をより良いものにするために、近日中に変更を行っており、利便性を向上 [さ](microsoft-secure-score.md) せています。 スコアと可能な最大スコアは変わる可能性があります。

## <a name="proposed-changes"></a>Proposed changes

### <a name="november-2020"></a>2020年11月

**> servicenow を共有** することによって、セキュリティで保護されたスコアで servicenow チケットを作成する機能を削除します。

- ServiceNow コネクタのプレビュー期間が終了します。 この機能は2020の終わりまでは利用できなくなります。 フィードバックをお寄せいただきありがとうございます。次の手順を決定しています。

エンドポイントの Microsoft Defender (以前の Microsoft Defender ATP) に関連する18の改善アクションを追加します。

Attack Surface Reduction (ASR) 関連の推奨事項:
- 電子メールクライアントおよび webmail からの実行可能ファイルのコンテンツをブロックする
- すべての Office アプリケーションで子プロセスを作成することを禁止する
- Office アプリケーションで実行可能なコンテンツを作成することを禁止する
- Office アプリケーションが他のプロセスにコードを挿入するのをブロックする
- JavaScript または VBScript がダウンロードされた実行可能コンテンツを起動するのをブロックする
- 難読化する可能性のあるスクリプトの実行をブロックする
- Office マクロからの Win32 API 呼び出しをブロックする
- 実行可能ファイルが、流行、年齢、または信頼できるリストの条件を満たしていない限り、実行を禁止する
- ランサムウェアに対する高度な保護の使用
- Windows ローカルセキュリティ機関サブシステムからの資格情報の盗用をブロックする (lsass.exe)
- PSExec および WMI コマンドからのプロセス作成をブロックする
- USB から実行される信頼できないおよび署名されていないプロセスをブロックする
- Office コミュニケーションアプリケーションによる子プロセスの作成を禁止する
- Adobe Reader が子プロセスを作成するのをブロックする
- WMI イベントサブスクリプション経由の永続化をブロックする

サービス関連の推奨事項:
- Windows サービスの引用符で囲まれるサービスパスを修正する
- サービスの実行可能パスを共通の保護された場所に変更する
- Windows レジストリでパスワードがキャッシュされないようにサービスアカウントを変更する

## <a name="related-resources"></a>関連リソース

- [Microsoft セキュリティスコアの概要](microsoft-secure-score.md)
- [セキュリティ体制にアクセス](microsoft-secure-score-improvement-actions.md)
- [Microsoft のセキュリティで保護されたスコア履歴を追跡し、目標を達成する](microsoft-secure-score-history-metrics-trends.md)
- [新機能](microsoft-secure-score-whats-new.md)
