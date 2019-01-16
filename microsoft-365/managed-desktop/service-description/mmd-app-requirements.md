---
title: Microsoft 管理されたデスクトップ アプリケーションの要件
description: ''
keywords: 管理されたデスクトップの Microsoft、Microsoft 365 サービス マニュアル
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 01/08/2019
ms.openlocfilehash: 6b6c6f6a2e719496578ac1d15c9b94a92a2ab492
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/16/2019
ms.locfileid: "26868983"
---
# <a name="microsoft-managed-desktop-app-requirements"></a>Microsoft 管理されたデスクトップ アプリケーションの要件

<!--This topic is the target for aka.ms/app-req. This is aka link is used from EA agreeement for MMD. do not delete.-->

<!--Application addendum -->
 
Microsoft 管理デスクトップ デバイスに配備する基幹業務アプリケーションでは、このトピックの要件を満たす必要があります。 

## <a name="application-condition"></a>アプリケーションの条件

アプリケーションは、Microsoft の管理されたデスクトップ環境に悪影響を及ぼすしない必要があります。アプリケーションは、マイクロソフトが展開するために満たす必要がある要件を次に示します。任意の特定のアプリケーションまたはドライバーを使用して、マイクロソフトは、ここに示すすべての要件を免除可能性があります。マイクロソフトは、アプリケーションまたはドライバーがマイクロソフトの管理されたデスクトップのデバイスのパフォーマンスと信頼性に悪影響を削除する場合があります。

## <a name="deployable-using-microsoft-technologies"></a>マイクロソフトのテクノロジを使用して配置可能です

Microsoft 管理されたデスクトップは、アプリケーションを配置するのに Intune、マイクロソフトのストア、およびビジネスのためのマイクロソフト ストアを使用します。したがって、これらのサービスで最新のバージョンで展開することの方法でアプリケーションをパッケージ化しなければなりません。

## <a name="prohibited-app-classes"></a>禁止されているアプリケーション クラス

Microsoft 管理デスクトップ デバイスでは、特定の種類のアプリケーションは使用できません。
- サード パーティ製ウイルス対策、セキュリティ、または監査ソフトウェア
- サード パーティ製の web ブラウザー
- Office 365 Pro Plus より前の Microsoft Office のバージョン
- アプリケーションをインストールするか、他のサード ・ パーティ製ソフトウェアをバンドル

## <a name="restricted-app-behaviors"></a>制限されたアプリケーションの動作

特定のアプリケーションの動作するユーザー エクスペリエンスに悪影響を及ぼすか、Microsoft 管理デスクトップ デバイスにセキュリティ リスクが存在します。アプリケーションは、次の動作または特性は発生しません。 

ユーザー エクスペリエンス。
- バック グラウンド サービスをインストールするか、長時間実行されるバック グラウンド プロセスの生成
- 自分自身を Windows のスタートアップ パスに追加します。

セキュリティ:
- Windows または Office の内部データ構造を文書化されていない、Windows または Office Api を呼び出すまたは依存関係
- アプリケーション ストアとして機能または拡張機能マネージャー
- エンド ・ ユーザーの権限を昇格させる
- 既知のセキュリティの脆弱性を持つ
- 重ね合わせ不可に信頼されたルート証明書を使用して署名
- 暗号化またはエンド ・ ユーザーのデータへのアクセスを制限
- 実行時にオペレーティング システムのコードを変更します。

## <a name="driver-deployment"></a>ドライバーの配備

場合を除き、ドライバーが Windows Update で利用可能な Windows ハードウェア品質ラボ (WHQL) によって署名とは別に、マイクロソフトは、マイクロソフトはマイクロソフトの管理されたデスクトップ デバイスにドライバーを配置する前にドライバーを承認する必要があります。
