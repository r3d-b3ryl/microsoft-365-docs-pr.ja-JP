---
title: データストレージとプライバシーをMicrosoft Defender for Endpointする
description: Microsoft Defender for Endpointが収集するプライバシーとデータを処理する方法について説明します。
keywords: Microsoft Defender for Endpoint、データストレージとプライバシー、ストレージ、プライバシー、ライセンス、位置情報、データ保持、データ
ms.prod: m365-security
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
ms.technology: mde
ms.openlocfilehash: d1d8ad0a16129e909476891291c0b2c0f0d54956
ms.sourcegitcommit: bc35c7826e3403f259725ac72cca5bafd36aa56a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/30/2022
ms.locfileid: "66554149"
---
# <a name="microsoft-defender-for-endpoint-data-storage-and-privacy"></a>データストレージとプライバシーをMicrosoft Defender for Endpointする

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-assignaccess-abovefoldlink)

このセクションでは、Defender for Endpoint のプライバシーとデータ処理に関してよく寄せられる質問の一部について説明します。

> [!NOTE]
> このドキュメントでは、Defender for Endpoint に関連するデータ ストレージとプライバシーの詳細について説明します。 Defender for Endpoint およびその他の製品やサービス (Microsoft Defender ウイルス対策や Windows など) に関連する詳細については、 [Microsoft のプライバシーに関する声明を](https://go.microsoft.com/fwlink/?linkid=827576)参照してください。 詳細については、 [Windows プライバシーに](https://go.microsoft.com/fwlink/?linkid=827577) 関する FAQ も参照してください。

## <a name="what-data-does-microsoft-defender-for-endpoint-collect"></a>収集Microsoft Defender for Endpointデータは何ですか?

Microsoft Defender for Endpointは、管理、追跡、およびレポートの目的で、サービスに固有の専用および分離されたテナントに、構成されたデバイスから情報を収集して格納します。

収集される情報には、ファイル データ (ファイル名、サイズ、ハッシュなど)、プロセス データ (実行中のプロセス、ハッシュ)、レジストリ データ、ネットワーク接続データ (ホスト IP とポート)、デバイスの詳細 (デバイス識別子、名前、オペレーティング システム のバージョンなど) が含まれます。

Microsoft は、このデータを Microsoft Azure に安全に保存し、Microsoft のプライバシープラクティスと [Microsoft Trust Center ポリシー](https://go.microsoft.com/fwlink/?linkid=827578)に従って保持します。

このデータにより、Defender for Endpoint は次のことが可能になります。

- 組織内の攻撃のインジケーター (IOA) を事前に特定する
- 攻撃の可能性が検出された場合にアラートを生成する
- ネットワークからの脅威信号に関連するデバイス、ファイル、URL に対するビューを使用してセキュリティ操作を提供し、ネットワーク上のセキュリティ脅威の存在を調査して調査できるようにします。

Microsoft は、お客様のデータを広告に使用しません。

## <a name="data-protection-and-encryption"></a>データ保護と暗号化

Defender for Endpoint サービスは、Microsoft Azure インフラストラクチャに基づく最新のデータ保護テクノロジを利用します。

サービスが処理するデータ保護には、さまざまな側面があります。 暗号化は最も重要なものの 1 つであり、保存時のデータ暗号化、フライト中の暗号化、Key Vaultによるキー管理が含まれます。 Defender for Endpoint サービスで使用されるその他のテクノロジの詳細については、 [Azure 暗号化の概要](/azure/security/security-azure-encryption-overview)に関するページを参照してください。

すべてのシナリオで、データは少なくとも 256 ビット [の AES 暗号化](https://en.wikipedia.org/wiki/Advanced_Encryption_Standard) を使用して暗号化されます。

## <a name="data-storage-location"></a>データの保存場所

Defender for Endpoint は、欧州連合、英国、または米国の Microsoft Azure データセンターで動作します。 サービスによって収集された顧客データは、(a) プロビジョニング中に識別されるテナントの地理的な場所、または (b) Defender for Endpoint が別の Microsoft オンライン サービスを使用してそのようなデータを処理する場合は、その他のオンライン サービスのデータ格納規則で定義されている位置情報に格納される場合があります。

仮名化された形式の顧客データは、米国の中央ストレージおよび処理システムに格納することもできます。

構成が完了すると、データの格納場所を変更することはできません。 これにより、データが存在する地理的な場所を積極的に選択することで、コンプライアンス リスクを最小限に抑える便利な方法が提供されます。

## <a name="is-my-data-isolated-from-other-customer-data"></a>自分のデータは他の顧客データから分離されていますか?

はい。データは、アクセス認証と、顧客識別子に基づく論理的な分離によって分離されます。 各顧客は、Microsoft が提供する独自の組織と汎用データから収集されたデータにのみアクセスできます。

## <a name="how-does-microsoft-prevent-malicious-insider-activities-and-abuse-of-high-privilege-roles"></a>Microsoft では、悪意のあるインサイダー アクティビティや高い特権ロールの悪用をどのように防止しますか?

Microsoft の開発者と管理者は、設計上、サービスを運用および進化させるために割り当てられた職務を遂行するための十分な特権を与えられています。 Microsoft は、承認されていない開発者や管理アクティビティから保護するために、次のメカニズムを含む予防、探偵、および事後対応の制御の組み合わせを展開しています。

- 機密データへの厳密なアクセス制御
- 悪意のあるアクティビティの独立した検出を大幅に強化するコントロールの組み合わせ
- 監視、ログ記録、およびレポートの複数のレベル

さらに、Microsoft は特定の運用担当者のバックグラウンド検証チェックを実施し、バックグラウンド検証のレベルに比例してアプリケーション、システム、ネットワーク インフラストラクチャへのアクセスを制限します。 運用担当者は、職務の遂行において顧客のアカウントまたは関連情報にアクセスする必要がある場合、正式なプロセスに従います。

Microsoft Azure Government データ センターにデプロイされたサービスのデータへのアクセスは、FedRAMP、NIST 800.171 (DIB)、ITAR、IRS 1075、DoD L4、CJIS など、特定の政府の規制と要件の対象となるデータを処理するためにスクリーニングされ、承認された運用担当者にのみ付与されます。

## <a name="is-data-shared-with-other-customers"></a>データは他の顧客と共有されますか?

いいえ。 顧客データは他の顧客から分離され、共有されません。 ただし、Microsoft の処理に起因し、顧客固有のデータを含まないデータに関する分析情報は、他の顧客と共有される可能性があります。 各顧客は、Microsoft が提供する独自の組織と汎用データから収集されたデータにのみアクセスできます。

## <a name="how-long-will-microsoft-store-my-data-what-is-microsofts-data-retention-policy"></a>Microsoft がデータを保存する期間はどのくらいですか? Microsoft のデータ保持ポリシーとは何ですか?

### <a name="at-service-onboarding"></a>サービスオンボーディング時

既定では、データは 180 日間保持されます。ただし、データのデータ保持ポリシーを指定できます。 これにより、Microsoft Defender for Endpointがデータを格納する期間が決まります。 会社の規制コンプライアンスのニーズを満たすために、1 か月から 6 か月の範囲で柔軟に選択できます。

### <a name="at-contract-termination-or-expiration"></a>契約の終了時または有効期限時

ライセンスが猶予期間または中断モードの間、データは保持され、利用できるようになります。 この期間の終わりに、そのデータは Microsoft のシステムから消去され、契約の終了または有効期限から 180 日以内に回復できなくなります。

### <a name="advanced-hunting-data"></a>高度なハンティング データ

高度な捜索は、クエリ ベースの脅威の捜索ツールで、最大 30 日間のロー データを検索できます。

## <a name="can-microsoft-help-us-maintain-regulatory-compliance"></a>Microsoft は、規制コンプライアンスの維持に役立ちますか?

Microsoft は、監査レポートやコンプライアンス パッケージを含む Microsoft のセキュリティおよびコンプライアンス プログラムに関する詳細情報をお客様に提供し、お客様が独自の法的および規制上の要件に照らして Defender for Endpoint サービスを評価するのに役立ちます。 Defender for Endpoint は、ISO、SOC、FedRAMP High、PCI など、さまざまな認定を取得しており、国内、地域、業界固有の追加の認定を引き続き推進しています。

Microsoft では、お客様に個別に検証された準拠したサービスを提供することで、お客様が実行するインフラストラクチャとアプリケーションのコンプライアンスを容易に実現できます。

Defender for Endpoint 認定レポートの詳細については、 [Microsoft トラスト センター](https://servicetrust.microsoft.com/)に関するページを参照してください。 

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-datastorage-belowfoldlink)
