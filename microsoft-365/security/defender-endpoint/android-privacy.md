---
title: Android 用 Microsoft Defender for Endpoint - プライバシー情報
description: プライバシー制御、プライバシーに影響を与えるポリシー設定を構成する方法、および Android 上の Microsoft Defender for Endpoint で収集された診断データに関する情報。
keywords: microsoft、 defender、 Microsoft Defender for Endpoint, android, privacy, diagnostic
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 8ab7bdba676c777faea87bfeb8eaddc0166b1319
ms.sourcegitcommit: d817a3aecb700f7227a05cd165ffa7dbad67b09d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/29/2021
ms.locfileid: "53651473"
---
#  <a name="microsoft-defender-for-endpoint-on-android---privacy-information"></a>Android 用 Microsoft Defender for Endpoint - プライバシー情報

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

Defender for Endpoint on Android は、構成済みの Android デバイスから情報を収集し、Defender for Endpoint がある同じテナントに保存します。 この情報は、Defender for Endpoint for Android をセキュリティで保護し、最新の状態に保ち、期待通り実行し、サービスをサポートするために収集されます。

データ ストレージの詳細については [、「Microsoft Defender for Endpoint data storage and privacy」を参照してください](data-storage-privacy.md)。

情報は、Defender for Endpoint for Android のセキュリティを確保し、最新の状態に保ち、期待通り実行し、サービスをサポートするために収集されます。

Android および iOS モバイル デバイスの Microsoft Defender for Endpoint に関する最も一般的なプライバシーに関する質問の詳細については [、「Microsoft Defender for Endpoint and your](https://support.microsoft.com/topic/microsoft-defender-for-endpoint-and-your-privacy-on-android-and-ios-mobile-devices-4109bc54-8ec5-4433-9c33-d359b75ac22a)privacy on Android and iOS mobile devices」を参照してください。

## <a name="required-data"></a>必須データ

必要なデータは、Android 用 Defender for Endpoint を期待通り動作させるのに必要なデータで構成されます。 このデータはサービスの運用に不可欠であり、エンド ユーザー、組織、デバイス、アプリに関連するデータを含めできます。 収集するデータの種類の一覧を次に示します。

### <a name="app-information"></a>アプリ情報

デバイス上 **の** 悪意のある Android アプリケーション パッケージ (APK) に関する情報 (以下を含む)

- ソースのインストール
- Storageの場所 (ファイル パス)
- インストールの時間、APK のサイズ、およびアクセス許可

### <a name="web-page--network-information"></a>Web ページ / ネットワーク情報

- 悪意のある接続または Web ページが検出された場合にのみ、Web サイトの完全な URL。
- 接続情報
- プロトコルの種類 (HTTP、HTTPS など)

### <a name="device-and-account-information"></a>デバイスとアカウントの情報

- 日付、時刻、Android & OEM モデル、CPU 情報、デバイス識別子などのデバイス情報。
- デバイス識別子は、次のいずれかを示します。
  - Wi-Fi MAC アドレス
  - [Android ID](https://developer.android.com/reference/android/provider/Settings.Secure#ANDROID_ID) (デバイスの初回起動時に Android によって生成されます)。
  - ランダムに生成されたグローバル一意識別子 (GUID)。

- テナント、デバイス、およびユーザー情報
  - Azure Active Directory (AD) デバイス ID と Azure ユーザー ID: デバイスを一意に識別します。ユーザーは、それぞれ Azure Active ディレクトリにあります。
  - Azure テナント ID: 組織内の組織を識別する GUID Azure Active Directory。
  - Microsoft Defender for Endpoint org ID: デバイスが属する企業に関連付けられた一意の識別子。 Microsoft は、問題が一部の企業に影響を与えるかどうか、および影響を受け取る企業の数を特定できます。
  - ユーザー プリンシパル名: ユーザーの電子メール ID

### <a name="product-and-service-usage-data"></a>製品とサービスの使用状況データ

次の情報は、デバイスにインストールされている Microsoft Defender for Endpoint アプリの場合にのみ収集されます。 

- 名前、バージョン、アプリアップグレードの状態を含むアプリ パッケージ情報。
- アプリで実行されるアクション。
- 脅威の検出情報 (脅威名、カテゴリなど)
- Android によって生成されたクラッシュ レポート ログ。

## <a name="optional-data"></a>オプションのデータ

オプションのデータには、診断データとフィードバック データが含まれます。 オプションの診断データは、製品の改良に役立ち、問題の検出、診断、修正に役立つ高度な情報を提供する追加データです。 オプションの診断データには、次の情報が含まれます。

- アプリ、CPU、およびネットワークの使用状況。
- アプリの観点からデバイスの状態 (スキャンの状態、スキャンのタイミング、付与されたアプリのアクセス許可、アップグレードの状態など)。
- 管理者が構成した機能。
- デバイス上のブラウザーに関する基本情報。

**フィードバック データは** 、ユーザーが提供するアプリ内フィードバックを通じて収集されます。

- ユーザーの電子メール アドレスを指定する場合。
- フィードバックの種類 (微笑み、顔をしかめ、アイデア) と、ユーザーが送信したフィードバックコメント。
