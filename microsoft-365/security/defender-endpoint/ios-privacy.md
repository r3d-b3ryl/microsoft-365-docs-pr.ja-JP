---
title: プライバシー情報 - Microsoft Defender for Endpoint on iOS
ms.reviewer: ''
description: iOS 上の Microsoft Defender for Endpoint のプライバシー情報について説明します。
keywords: microsoft、 defender、 Microsoft Defender for Endpoint, ios, policy, overview
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 4fc5d4fb51170a70edc8664d5ccba0943b93353d
ms.sourcegitcommit: dfa9f28a5a5055a9530ec82c7f594808bf28d0dc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/29/2021
ms.locfileid: "61217388"
---
# <a name="privacy-information---microsoft-defender-for-endpoint-on-ios"></a>プライバシー情報 - Microsoft Defender for Endpoint on iOS

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)

> [!NOTE]
> iOS のエンドポイントの Defender は、VPN を使用して Web 保護機能を提供します。 これは通常の VPN ではなく、デバイスの外部でトラフィックを受け取らないローカルまたは自己ループ VPN です。 **Microsoft または組織では、閲覧アクティビティが表示されない。**

iOS のエンドポイント用 Defender は、構成済みの iOS デバイスから情報を収集し、Defender for Endpoint を持つ同じテナントに格納します。 この情報は、IOS の Defender for Endpoint をセキュリティで保護し、最新の状態に保ち、期待通り実行し、サービスをサポートするために収集されます。

データ ストレージの詳細については [、「Microsoft Defender for Endpoint data storage and privacy」を参照してください](data-storage-privacy.md)。

Android および iOS モバイル デバイスの Microsoft Defender for Endpoint に関する最も一般的なプライバシーに関する質問の詳細については [、「Microsoft Defender for Endpoint and your](https://support.microsoft.com/topic/microsoft-defender-for-endpoint-and-your-privacy-on-android-and-ios-mobile-devices-4109bc54-8ec5-4433-9c33-d359b75ac22a)privacy on Android and iOS mobile devices」を参照してください。

## <a name="required-data"></a>必須データ

必要なデータは、iOS の Defender for Endpoint を期待通り動作させるのに必要なデータで構成されます。 このデータはサービスの運用に不可欠であり、エンド ユーザー、組織、デバイス、アプリに関連するデータを含めできます。

収集するデータの種類の一覧を次に示します。

### <a name="web-page-or-network-information"></a>Web ページまたはネットワーク情報

- 悪意のある接続または Web ページが検出された場合にのみ、Web サイトのドメイン名と IP アドレス。

### <a name="device-and-account-information"></a>デバイスとアカウントの情報

- 日付、時刻、iOS & CPU 情報、デバイス識別子などのデバイス情報 (デバイス識別子は次の 1 つ) です。
  - Wi-Fi MAC アドレス
  - ランダムに生成されたグローバル一意識別子 (GUID)
- テナント、デバイス、およびユーザー情報
  - Azure Active Directory (AD) デバイス ID と Azure ユーザー ID - デバイスを一意に識別します。ユーザーは、それぞれ Azure Active directory にあります。
  - Azure テナント ID - 組織内の組織を識別する GUID Azure Active Directory。
  - Microsoft Defender for Endpoint org ID - デバイスが属する企業に関連付けられた一意の識別子。 Microsoft は、企業の選択セットと影響を受ける企業の数に影響を与える問題が発生した場合の識別を許可します。
  - ユーザー プリンシパル名 - ユーザーの電子メール ID。

### <a name="product-and-service-usage-data"></a>製品とサービスの使用状況データ

次の情報は、デバイスにインストールされている Microsoft Defender for Endpoint アプリの場合にのみ収集されます。

- 名前、バージョン、アプリアップグレードの状態を含むアプリ パッケージ情報。
- アプリで実行されるアクション。
- iOS によって生成されたクラッシュ レポート ログ。
- メモリ使用量データ。

## <a name="optional-data"></a>オプションのデータ

オプションのデータには、クライアントからの診断データとフィードバック データが含まれます。 オプションの診断データは、製品の改良に役立ち、問題の検出、診断、修正に役立つ高度な情報を提供する追加データです。 このデータは診断のみを目的としますが、サービス自体には必要ありません。

オプションの診断データには、次の情報が含まれます。

- Defender for Endpoint のアプリ、CPU、およびネットワーク使用率。
- Defender for Endpoint 用に管理者が構成した機能。

フィードバック データは、ユーザーが提供するアプリ内フィードバックを通じて収集されます。

- ユーザーの電子メール アドレスを指定する場合。
- フィードバックの種類 (微笑み、顔をしかめ、アイデア) と、ユーザーが送信したフィードバックコメント。

詳細については、「プライバシーの詳細 [」を参照してください](https://aka.ms/mdatpiosprivacystatement)。
