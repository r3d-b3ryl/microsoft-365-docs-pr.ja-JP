---
title: Microsoft Defender for Endpoint データストレージとプライバシー
description: Microsoft Defender for Endpoint が収集するプライバシーとデータを処理する方法について説明します。
keywords: Microsoft Defender for Endpoint, data storage and privacy, storage, privacy, licensing, geolocation, data retention, data
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
ms.openlocfilehash: 70607eb90fa6c1614ed10e90e4d6ee9cf36f7204
ms.sourcegitcommit: 87d994407fb69a747239b8589ad11ddf9b47e527
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2021
ms.locfileid: "53595704"
---
# <a name="microsoft-defender-for-endpoint-data-storage-and-privacy"></a>Microsoft Defender for Endpoint データストレージとプライバシー

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を体験してみませんか? [無料試用版にサインアップしてください。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

このセクションでは、Defender for Endpoint のプライバシーとデータ処理に関してよく寄せられる質問について説明します。

> [!NOTE]
> このドキュメントでは、Defender for Endpoint に関連するデータストレージとプライバシーの詳細について説明します。 Defender for Endpoint および他の製品およびサービス (Microsoft Defender ウイルス対策 および Windows 10に関する詳細については[、「Microsoft Privacy Statement」を参照してください](https://go.microsoft.com/fwlink/?linkid=827576)。 詳細については[、「Windows 10 FAQ」](https://go.microsoft.com/fwlink/?linkid=827577)を参照してください。

## <a name="what-data-does-microsoft-defender-for-endpoint-collect"></a>Microsoft Defender for Endpoint が収集するデータは何ですか?

Microsoft Defender for Endpoint は、管理、追跡、およびレポートの目的でサービスに固有の、構成済みのデバイスから、サービス固有の専用テナントおよび分離テナントに情報を収集して保存します。

収集される情報には、ファイル データ (ファイル名、サイズ、ハッシュなど)、プロセス データ (実行中のプロセス、ハッシュ)、レジストリ データ、ネットワーク接続データ (ホスト IP とポート)、デバイスの詳細 (デバイス識別子、名前、オペレーティング システムのバージョンなど) が含まれます。

Microsoft は、このデータをセキュリティで保護Microsoft Azure、Microsoft のプライバシープラクティスと Microsoft Trust Center ポリシーに従[って管理します](https://go.microsoft.com/fwlink/?linkid=827578)。

このデータを使用すると、Defender for Endpoint は次の操作を実行できます。

- 組織内の攻撃の指標 (IOA) を積極的に特定する
- 攻撃の可能性が検出された場合にアラートを生成する
- ネットワークからの脅威信号に関連するデバイス、ファイル、URL を確認してセキュリティ操作を提供し、ネットワーク上のセキュリティ脅威の存在を調査し、調査することができます。

Microsoft は広告にデータを使用しない。

## <a name="data-protection-and-encryption"></a>データ保護と暗号化

Defender for Endpoint サービスは、最新のデータ保護テクノロジを利用し、最新のインフラストラクチャに基Microsoft Azureします。

弊社のサービスが管理するデータ保護に関連するさまざまな側面があります。 暗号化は最も重要な 1 つであり、保存時のデータ暗号化、飛行中の暗号化、Key Vault によるキー管理が含まれます。 Defender for Endpoint サービスで使用される他のテクノロジの詳細については、「Azure 暗号化の [概要」を参照してください](/azure/security/security-azure-encryption-overview)。

すべてのシナリオで、データは最小で 256 ビット [の AES 暗号化](https://en.wikipedia.org/wiki/Advanced_Encryption_Standard) を使用して暗号化されます。

## <a name="data-storage-location"></a>データの保存場所

Defender for Endpoint は、Microsoft Azure、英国、または米国のデータセンターで動作します。 サービスによって収集された顧客データは、(a) プロビジョニング中に特定されたテナントの地理的位置、または (b) Defender for Endpoint が別の Microsoft オンライン サービスを使用してそのようなデータを処理する場合、その他のオンライン サービスのデータストレージ ルールで定義される地理的位置に格納されます。

仮名化された形式の顧客データは、米国の中央ストレージおよび処理システムに保存される場合があります。

構成が完了すると、データの保存場所を変更できません。 これにより、データが存在する地理的な場所を積極的に選択することで、コンプライアンス リスクを最小限に抑える便利な方法が提供されます。

## <a name="is-my-data-isolated-from-other-customer-data"></a>自分のデータは他の顧客データから分離されていますか?

はい、データはアクセス認証と顧客識別子に基づく論理的な分離によって分離されます。 各顧客は、Microsoft が提供する独自の組織および汎用データから収集されたデータにのみアクセスできます。

## <a name="how-does-microsoft-prevent-malicious-insider-activities-and-abuse-of-high-privilege-roles"></a>Microsoft は、悪意のあるインサイダーアクティビティや特権の高い役割の悪用を防止する方法を説明します。

Microsoft の開発者と管理者は、設計上、サービスの運用と進化のために割り当てられた職務を遂行するのに十分な特権を与えら た。 Microsoft では、承認されていない開発者や管理活動から保護するために、次のメカニズムを含む予防、探偵、および反応性の制御の組み合わせを展開しています。

- 機密データへの厳しいアクセス制御
- 悪意のあるアクティビティの独立した検出を大幅に強化するコントロールの組み合わせ
- 複数のレベルの監視、ログ、およびレポート

さらに、Microsoft は特定の運用担当者のバックグラウンド検証チェックを実施し、バックグラウンド検証のレベルに応じてアプリケーション、システム、およびネットワーク インフラストラクチャへのアクセスを制限します。 運用担当者は、業務の遂行中に顧客のアカウントまたは関連情報にアクセスする必要がある場合、正式なプロセスに従います。

Microsoft Azure Government データ センターに展開されるサービスのデータへのアクセスは、FedRAMP、NIST 800.171 (DIB)、ITAR、IRS 1075、DoD L4、CJIS など、特定の政府の規制および要件の対象となるデータの処理を承認された運用担当者にのみ付与されます。

## <a name="is-data-shared-with-other-customers"></a>データは他の顧客と共有されていますか?

いいえ。 顧客データは他の顧客から分離され、共有されません。 ただし、Microsoft の処理に起因するデータ、および顧客固有のデータを含むデータに関する分析情報は、他の顧客と共有される場合があります。 各顧客は、Microsoft が提供する独自の組織および汎用データから収集されたデータにのみアクセスできます。

## <a name="how-long-will-microsoft-store-my-data-what-is-microsofts-data-retention-policy"></a>Microsoft は自分のデータを保存する期間を指定します。 Microsoft のデータ保持ポリシーとは

### <a name="at-service-onboarding"></a>サービスオンボーディング時

既定では、データは 180 日間保持されます。ただし、データのデータ保持ポリシーを指定できます。 これにより、Window Defender for Endpoint がデータを保存する期間が決されます。 会社の規制コンプライアンスニーズを満たすために、1 か月から 6 か月の範囲で柔軟に選択できます。

### <a name="at-contract-termination-or-expiration"></a>契約の終了または有効期限時

ライセンスが猶予期間または中断モードの間、データは保持され、利用できます。 この期間の終わりに、そのデータは Microsoft のシステムから消去され、契約の終了または有効期限から 180 日以内に回復不能になります。

### <a name="advanced-hunting-data"></a>高度なハンティング データ

高度な捜索は、クエリ ベースの脅威の捜索ツールで、最大 30 日間のロー データを検索できます。

## <a name="can-microsoft-help-us-maintain-regulatory-compliance"></a>Microsoft は、規制コンプライアンスの維持に役立ちますか?

Microsoft は、Microsoft のセキュリティおよびコンプライアンス プログラムに関する詳細な情報 (監査レポートやコンプライアンス パッケージなど) を提供し、お客様が Defender for Endpoint サービスを独自の法的および規制上の要件に対して評価するのに役立ちます。 Defender for Endpoint は、ISO、SOC、FedRAMP High、PCI などの多くの認定を取得し、国内、地域、業界固有の追加の認定を引き続き追求しています。

Microsoft は、コンプライアンスに準拠した個別に検証されたサービスを顧客に提供することで、お客様が実行するインフラストラクチャとアプリケーションのコンプライアンスを簡単に実現できます。

Defender for Endpoint 認定レポートの詳細については [、「Microsoft Trust Center」を参照してください](https://servicetrust.microsoft.com/)。 

> Defender for Endpoint を体験してみませんか? [無料試用版にサインアップしてください。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-datastorage-belowfoldlink)
