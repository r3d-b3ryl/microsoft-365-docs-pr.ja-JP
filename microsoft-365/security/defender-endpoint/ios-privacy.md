---
title: プライバシー情報 - iOS でのMicrosoft Defender for Endpoint
ms.reviewer: ''
description: iOS でのMicrosoft Defender for Endpointのプライバシー情報について説明します
keywords: microsoft, defender, Microsoft Defender for Endpoint, ios, policy, overview
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
# <a name="privacy-information---microsoft-defender-for-endpoint-on-ios"></a>プライバシー情報 - iOS でのMicrosoft Defender for Endpoint

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)

> [!NOTE]
> iOS 上の Defender for Endpoint では、VPN を使用して Web 保護機能を提供します。 これは通常の VPN ではなく、デバイスの外部でトラフィックを受け取らないローカルまたは自己ループ VPN です。 **Microsoft または組織では、閲覧アクティビティは表示されません。**

iOS 上の Defender for Endpoint は、構成された iOS デバイスから情報を収集し、Defender for Endpoint があるのと同じテナントに格納します。 この情報は、iOS 上の Defender for Endpoint をセキュリティで保護し、最新の状態に保ち、期待どおりに実行し、サービスをサポートするために収集されます。

データ ストレージの詳細については、「データ ストレージ[とプライバシー Microsoft Defender for Endpoint](data-storage-privacy.md)」を参照してください。

Android および iOS モバイル デバイスのMicrosoft Defender for Endpointに関する最も一般的なプライバシーに関する質問の詳細については、[Android および iOS モバイル デバイスでのMicrosoft Defender for Endpointとプライバシーに関するページを](https://support.microsoft.com/topic/microsoft-defender-for-endpoint-and-your-privacy-on-android-and-ios-mobile-devices-4109bc54-8ec5-4433-9c33-d359b75ac22a)参照してください。

## <a name="required-data"></a>必須データ

必要なデータは、iOS 上の Defender for Endpoint を期待どおりに動作させるために必要なデータで構成されます。 このデータは、サービスの運用に不可欠であり、エンド ユーザー、組織、デバイス、アプリに関連するデータを含めることができます。

収集されるデータの種類の一覧を次に示します。

### <a name="web-page-or-network-information"></a>Web ページまたはネットワーク情報

- 悪意のある接続または Web ページが検出された場合にのみ、Web サイトのドメイン名と IP アドレス。

### <a name="device-and-account-information"></a>デバイスとアカウントの情報

- 日付&時刻、iOS バージョン、CPU 情報、デバイス識別子などのデバイス情報 。デバイス識別子は次のいずれかです。
  - Wi-Fi アダプターの MAC アドレス
  - ランダムに生成されたグローバル一意識別子 (GUID)
- テナント、デバイス、ユーザーの情報
  - Azure Active Directory (AD) デバイス ID と Azure ユーザー ID - Azure Active directory でデバイスをそれぞれ一意に識別します。
  - Azure テナント ID - Azure Active Directory内の組織を識別する GUID。
  - Microsoft Defender for Endpoint組織 ID - デバイスが属するエンタープライズに関連付けられている一意の識別子。 Microsoft は、選択した一連の企業と影響を受ける企業の数に影響を与える問題があるかどうかを特定できます。
  - ユーザー プリンシパル名 - ユーザーの電子メール ID。

### <a name="product-and-service-usage-data"></a>製品とサービスの使用状況データ

次の情報は、デバイスにインストールされているMicrosoft Defender for Endpoint アプリに対してのみ収集されます。

- 名前、バージョン、アプリのアップグレード状態など、アプリ パッケージ情報。
- アプリで実行されるアクション。
- iOS によって生成されたクラッシュ レポート ログ。
- メモリ使用量データ。

## <a name="optional-data"></a>省略可能なデータ

オプション データには、クライアントからの診断データとフィードバック データが含まれます。 オプションの診断データは、製品の改良に役立ち、問題の検出、診断、修正に役立つ高度な情報を提供する追加データです。 このデータは診断のみを目的としており、サービス自体には必要ありません。

オプションの診断データには、次のものが含まれます。

- Defender for Endpoint のアプリ、CPU、ネットワークの使用状況。
- Defender for Endpoint の管理者によって構成された機能。

フィードバック データは、ユーザーが提供するアプリ内フィードバックを通じて収集されます。

- ユーザーの電子メール アドレス (ユーザーが指定を選択した場合)。
- フィードバックの種類 (笑顔、しかめ、アイデア)、およびユーザーが送信したフィードバック コメント。

詳細については、「 [プライバシーの詳細」を](https://aka.ms/mdatpiosprivacystatement)参照してください。
