---
title: Microsoft マネージドデスクトップアプリの要件
description: ''
keywords: microsoft マネージドデスクトップ、microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 01/08/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: de6cc7d77e023a9d41961e5fbcce060f1bb659ae
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32278337"
---
# <a name="microsoft-managed-desktop-app-requirements"></a>Microsoft マネージドデスクトップアプリの要件

<!--This topic is the target for aka.ms/app-req. This is aka link is used from EA agreeement for MMD. do not delete.-->

<!--Application addendum -->
 
Microsoft マネージドデスクトップデバイスに展開する基幹業務アプリケーションは、このトピックの要件を満たしている必要があります。 

## <a name="application-condition"></a>アプリケーションの条件

アプリケーションが Microsoft マネージドデスクトップ環境に悪影響を与えることは重要ではありません。 以下に、Microsoft が展開するためにアプリケーションが満たす必要がある要件を示します。 特定のアプリケーションまたはドライバーについては、ここに記載されているすべての要件を Microsoft が免除することがあります。 microsoft は、microsoft マネージドデスクトップデバイスのパフォーマンスと信頼性に悪影響を及ぼすアプリケーションまたはドライバーを削除することを決定する場合があります。

## <a name="deployable-using-microsoft-technologies"></a>Microsoft テクノロジを使用した展開

microsoft マネージドデスクトップでは、アプリケーションを展開するために Intune、microsoft store、および microsoft store を使用しています。 そのため、アプリケーションは、これらのサービスの最新バージョンによって展開可能な方法でパッケージ化する必要があります。

## <a name="prohibited-app-classes"></a>禁止されたアプリクラス

Microsoft マネージドデスクトップデバイスでは、特定の種類のアプリケーションが許可されていません。
- サードパーティ製のウイルス対策、セキュリティ、または監査ソフトウェア
- サードパーティの web ブラウザー
- office 365 Pro Plus より前のバージョンの Microsoft office
- 他のサードパーティ製ソフトウェアをインストールまたはバンドルするアプリケーション

## <a name="restricted-app-behaviors"></a>制限されたアプリの動作

アプリケーションの動作によっては、ユーザーの作業に悪影響を及ぼすことがあります。また、Microsoft マネージドデスクトップデバイスに対するセキュリティリスクを提示することもできます。 アプリケーションは、次の動作や特性を示しません。 

ユーザーの作業状況:
- バックグラウンドサービスをインストールする、または長時間実行するバックグラウンドプロセスを生成する
- Windows スタートアップパスに自分自身を追加する

セキュリティ:
- 文書化される windows または office api を呼び出したり、内部の windows または office データ構造に依存関係を取得したりする
- アプリストアとして機能するか、または組み込みの拡張機能マネージャーを備えている
- エンドユーザーの権限を昇格させる
- 既知のセキュリティの脆弱性
- 信頼できるルートにロールアップしない証明書を使用した署名
- エンドユーザーデータへのアクセスを暗号化または制限する
- 実行時にオペレーティングシステムのコードを変更する

## <a name="driver-deployment"></a>ドライバーの展開

ドライバーが windows Update で利用できない場合、または windows ハードウェア品質ラボ (WHQL) によって個別に署名されていない場合、microsoft がドライバーを microsoft マネージドデスクトップデバイスに展開する前に、microsoft がドライバーを承認する必要があります。
