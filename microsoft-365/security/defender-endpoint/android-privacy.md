---
title: Android 用 Microsoft Defender for Endpoint - プライバシー情報
description: プライバシー制御、Android 上のMicrosoft Defender for Endpointで収集された診断データに関するプライバシーと情報に影響を与えるポリシー設定を構成する方法。
keywords: microsoft, defender, Microsoft Defender for Endpoint, android, privacy, diagnostic
ms.service: microsoft-365-security
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
ms.subservice: mde
ms.openlocfilehash: 204d4c4bb2549d78b601e1e91c31ace16edf475a
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2022
ms.locfileid: "67475506"
---
# <a name="microsoft-defender-for-endpoint-on-android---privacy-information"></a>Android 用 Microsoft Defender for Endpoint - プライバシー情報

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

Android 上の Defender for Endpoint は、構成された Android デバイスから情報を収集し、Defender for Endpoint があるのと同じテナントに格納します。 この情報は、Defender for Endpoint for Android をセキュリティで保護し、最新の状態に保ち、期待どおりに実行し、サービスをサポートするために収集されます。

データ ストレージの詳細については、「データ ストレージ[とプライバシー Microsoft Defender for Endpoint](data-storage-privacy.md)」を参照してください。

情報は、Defender for Endpoint for Android をセキュリティで保護し、最新の状態に保ち、期待どおりに実行し、サービスをサポートするために収集されます。

Android および iOS モバイル デバイスのMicrosoft Defender for Endpointに関する最も一般的なプライバシーに関する質問の詳細については、[Android および iOS モバイル デバイスでのMicrosoft Defender for Endpointとプライバシーに関するページを](https://support.microsoft.com/topic/microsoft-defender-for-endpoint-and-your-privacy-on-android-and-ios-mobile-devices-4109bc54-8ec5-4433-9c33-d359b75ac22a)参照してください。

## <a name="required-data"></a>必要なデータ

必要なデータは、Defender for Endpoint for Android を期待どおりに動作させるために必要なデータで構成されます。 このデータは、サービスの運用に不可欠であり、エンド ユーザー、組織、デバイス、アプリに関連するデータを含めることができます。 収集されるデータの種類の一覧を次に示します。

### <a name="app-information"></a>アプリ情報

デバイス上の **悪意のある** Android アプリケーション パッケージ (APK) に関する情報 (以下を含む)

- ソースのインストール
- APK のストレージの場所 (ファイル パス)
- インストールの時間、APK のサイズ、アクセス許可

Android Enterprise フル マネージド デバイスの場合 - デバイスにインストールされている Android アプリケーション パッケージ (APK) に関する情報 (以下を含む)

- アプリの名前とパッケージ名
- アプリのバージョン番号
- ベンダー名

仕事用プロファイルを持つ Android Enterprise の場合 - デバイスの Work プロファイルにインストールされている Android アプリケーション パッケージ (APK) に関する情報 (以下を含む)

- アプリの名前とパッケージ名
- アプリのバージョン番号
- ベンダー名

*組織では、デバイスにインストールされているすべてのアプリに関する情報を送信するように Defender for Endpoint を構成することもできます。既定では、この情報は組織に送信されません。*


### <a name="web-page--network-information"></a>Web ページ/ネットワーク情報

- 悪意のある接続または Web ページが検出されてブロックされた場合にのみ、Web サイトの完全な URL。
- 接続情報
- プロトコルの種類 (HTTP、HTTPS など)

### <a name="device-and-account-information"></a>デバイスとアカウントの情報

- 日付&時刻、Android バージョン、OEM モデル、CPU 情報、デバイス識別子などのデバイス情報。
- デバイス識別子は次のいずれかです。
  - Wi-Fi アダプターの MAC アドレス
  - [Android ID](https://developer.android.com/reference/android/provider/Settings.Secure#ANDROID_ID) (デバイスの初回起動時に Android によって生成されます)。
  - ランダムに生成されたグローバル一意識別子 (GUID)。

- テナント、デバイス、ユーザーの情報
  - Azure Active Directory (AD) デバイス ID と Azure ユーザー ID: デバイスをそれぞれ Azure Active Directory のユーザーとして一意に識別します。
  - Azure テナント ID: Azure Active Directory 内の組織を識別する GUID。
  - Microsoft Defender for Endpoint組織 ID: デバイスが属する企業に関連付けられている一意の識別子。 Microsoft は、問題が一連の企業に影響を与えているかどうか、および影響を受ける企業の数を特定できます。
  - ユーザー プリンシパル名: ユーザーのEmail ID

### <a name="product-and-service-usage-data"></a>製品とサービスの使用状況データ

次の情報は、デバイスにインストールされているMicrosoft Defender for Endpoint アプリに対してのみ収集されます。 

- 名前、バージョン、アプリのアップグレード状態など、アプリ パッケージ情報。
- アプリで実行されるアクション。
- 脅威の検出情報 (脅威名、カテゴリなど)。
- Android によって生成されたクラッシュ レポート ログ。

## <a name="optional-data"></a>省略可能なデータ

省略可能なデータには、診断データとフィードバック データが含まれます。 オプションの診断データは、製品の改良に役立ち、問題の検出、診断、修正に役立つ高度な情報を提供する追加データです。 オプションの診断データには、次のものが含まれます。

- アプリ、CPU、およびネットワークの使用状況。
- スキャンの状態、スキャンのタイミング、付与されたアプリのアクセス許可、アップグレード状態など、アプリの観点からのデバイスの状態。
- 管理者によって構成された機能。
- デバイス上のブラウザーに関する基本情報。

**フィードバック データ** は、ユーザーが提供するアプリ内フィードバックを通じて収集されます

- ユーザーの電子メール アドレス (ユーザーが指定を選択した場合)。
- フィードバックの種類 (笑顔、しかめ、アイデア)、およびユーザーが送信したフィードバック コメント。
