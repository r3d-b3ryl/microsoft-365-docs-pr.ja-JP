---
title: Microsoft 365 のエンドポイントのデータ損失防止について説明する
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/21/2020
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: 'Microsoft 365 のエンドポイントのデータ損失防止は、ファイル アクティビティの監視と、それらのファイルに対する保護アクションをエンドポイントに拡張します。 Microsoft 365 のコンプライアンスソリューションでファイルが表示されます '
ms.openlocfilehash: 1dac32505144c3966ad2219cc69a33ba29f194dc
ms.sourcegitcommit: 29eb89b8ba0628fbef350e8995d2c38369a4ffa2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/15/2020
ms.locfileid: "49682628"
---
# <a name="learn-about-microsoft-365-endpoint-data-loss-prevention"></a>Microsoft 365 のエンドポイントのデータ損失防止について説明する

Microsoft 365 のデータ損失防止 (DLP) を使用すると、機密があると判断されたアイテムに対して、発生しているアクションを監視し、それらのアイテムの意図しない共有を防ぐことができます。 DLP の詳細については、「[データ損失防止ポリシーの概要](data-loss-prevention-policies.md)」を参照してください。

**エンドポイントデータ損失防止** (エンドポイント DLP) は、Windows 10 デバイスにある機密アイテムについて、DLP のアクティビティの監視と保護機能を拡張します。 デバイスが、 Microsoft 365 コンプライアンス ソリューションに オンボードすると、機密アイテムを使用してユーザーが行っていることに関する情報が[Activity Explorer](data-classification-activity-explorer.md)に表示され、[DLPポリシー](create-test-tune-dlp-policy.md)を通して、それらのアイテムに保護アクションを適用できます。

## <a name="endpoint-activities-you-can-monitor-and-take-action-on"></a>監視と対処が必要なエンドポイントのアクティビティ

Microsoft エンドポイント DLP を使用すると、Windows 10 を実行しているデバイスでユーザーが機密アイテムに行っている次のようなアクティビティを監査および管理できます。　　　


|アクティビティ |説明  | 監査可能/制限可能|
|---------|---------|---------|
|クラウド サービスへのアップロード、または許可されていないブラウザーによるアクセス    | ユーザーが制限されたサービス ドメインにアイテムをアップロードしようとした場合、またはブラウザーを介してアイテムにアクセスしようとした場合に検出します。  DLP に許可されていないブラウザーとしてリストされているブラウザーを使用している場合、アップロード アクティビティはブロックされ、ユーザーは Microsoft Edge (Chromium) を使用するようにリダイレクトされます。 その後、Microsoft Edge (Chromium) では、DLP ポリシー構成に基づいて、アップロードまたはアクセスを許可またはブロックします         |監査可能/制限可能|
|他のアプリへのコピー    |ユーザーが保護されたアイテムから情報をコピーし、他のアプリ、プロセス、またはアイテムに貼り付けようとした場合に検出します。 同一のアプリ、プロセス、またはアイテム内での情報のコピーと貼り付けは、このアクティビティでは検出されません。         | 監査可能/制限可能|
|USB リムーバブル メディアへのコピー |ユーザーがアイテムまたは情報をリムーバブル メディアまたは USB デバイスにコピーしようとした場合に検出します。         | 監査可能/制限可能|
|ネットワーク共有へのコピー    |ユーザーがアイテムをネットワーク共有またはマップされたネットワーク ドライブにコピーしようとした場合に検出します         |監査可能/制限可能|
|ドキュメントの印刷    |ユーザーが保護されたアイテムをローカル プリンターまたはネットワーク プリンターに出力しようとした場合に検出します。| 監査可能/制限可能         |
|アイテムの作成|ユーザーがアイテムを作成した場合に検出します| 監査可能|
|アイテムの名前の変更|ユーザーがアイテムの名前を変更した場合に検出します| 監査可能|


## <a name="whats-different-in-endpoint-dlp"></a>エンドポイント DLP との違い

エンドポイント DLP を掘り下げる前に知っておく必要がある追加の概念がいくつかあります。

### <a name="enabling-device-management"></a>デバイス管理を有効にする

デバイス管理は、デバイスからテレメトリを収集できる機能です。これは、エンドポイント DLP や [インサイダー リスク管理](insider-risk-management.md)などの 365 Microsoft のコンプライアンスソリューションに導入する機能です。 DLP ポリシーの場所として使用するすべてのデバイスをオンボードする必要があります。

> [!div class="mx-imgBorder"]
> ![デバイス管理を有効にする](../media/endpoint-dlp-learn-about-1-enable-device-management.png)

オンボードとオフボードは、デバイス管理センターからダウンロードするスクリプトを通して処理されます。 センターには、次の展開方法ごとにカスタムスクリプトがあります：

- ローカルスクリプト (最大10台のマシン)
- グループ ポリシー
- System Center Configuration Manager （ バージョン 1610以降 ）
- Mobile Device Management/Microsoft Intune
- 非永続的マシン用の VDI のオンボードスクリプト

> [!div class="mx-imgBorder"]
> ![デバイス オンボード ページ](../media/endpoint-dlp-learn-about-3-device-onboarding-page.png)

 デバイスをオンボードにするには、[Microsoft 365 エンドポイント DLPの使用を開始する](endpoint-dlp-getting-started.md)の手順を使用します。

[Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/) を介してデバイスをオンボードした場合、それらのデバイスは自動的にデバイスの一覧に表示されます。

> [!div class="mx-imgBorder"]
> ![管理対象デバイスの一覧](../media/endpoint-dlp-learn-about-2-device-list.png)

### <a name="viewing-endpoint-dlp-data"></a>エンドポイント DLP データの表示

 エンドポイント DLP は MIME タイプに基づいてアクティビティを監視するため、ファイルの拡張子が変更されてもアクティビティはキャプチャされます。 現時点では、次のファイル タイプがサポートされています。

- Word ファイル
- PowerPoint ファイル
- Excel ファイル
- PDF ファイル
- .csv ファイル
- .tsv ファイル
- .txt ファイル
- .rtf ファイル
- .c ファイル
- .class ファイル
- .cpp ファイル
- .cs ファイル
- .h ファイル
- .java ファイル

> [!NOTE]
> エンドポイント DLP は、上記すべての種類のファイルを DLP ポリシーに対して評価し、それに応じた保護アクションを適用します。 DLP ポリシーに一致するすべてのファイルは、たとえブロックされていなくても、サポートされているすべてのアクションについて監査されます。 さらに、Word、PowerPoint、Excel、PDF、.csv ファイルに対して実行されたファイル アクティビティについては、DLP ポリシーの存在やこれらのファイル対する一致に関係なく、既定で監査されます。

[DLP 警告管理ダッシュボード](dlp-configure-view-alerts-policies.md)に移動すると、エンドポイント デバイスに適用されている DLP ポリシーに関連する警告を表示できます。

![警告情報](../media/Alert-info-1.png)

同じダッシュボードで、リッチ メタデータに関連付けられたイベントの詳細を表示することもできます

![イベント情報](../media/Event-info-1.png)

デバイスがオンボードされると、場所としてデバイスを使用する DLP ポリシーを構成し、展開する前でも、監査されたアクティビティに関する情報がアクティビティエクスプローラーに流れます。

> [!div class="mx-imgBorder"]
> ![アクティビティ エクスプローラーでのエンドポイント DLP イベント](../media/endpoint-dlp-learn-about-4-activity-explorer.png)

エンドポイント DLP は、監査済みアクティビティに関する広範囲にわたる情報を収集します。

たとえば、ファイルがリムーバブル USB メディアにコピーされた場合、アクティビティの詳細に次の属性が表示されます：

- アクティビティの種類
- クライアント IP
- 対象ファイルのパス
- 発生したタイムスタンプ
- ファイル名
- ユーザー
- ファイル拡張子
- ファイル サイズ
- 機密情報の種類（該当する場合）
- sha1 値
- sha256 値
- 以前のファイル名
- 場所
- 親
- FilePath
- ソースの場所の種類
- platform
- デバイス名
- 場所の宛先の種類
- コピーを実行したアプリケーション
- Microsoft Defender for Endpoint デバイス ID (該当する場合)
- リムーバブルメディアデバイスの製造元
- リムーバブルメディアデバイスのモデル
- リムーバブルメディアデバイスのシリアル番号

> [!div class="mx-imgBorder"]
> ![USB アクティビティ属性へのコピー](../media/endpoint-dlp-learn-about-5-activity-attributes.png)

## <a name="next-steps"></a>次の手順

ここまでエンドポイント DLP について学びましたので、次のステップの手順は以下になります：

1) [Microsoft エンドポイント データ損失防止を開始する](endpoint-dlp-getting-started.md)
2) [Microsoft エンドポイント データ損失防止を使用する](endpoint-dlp-using.md)

## <a name="see-also"></a>関連項目

- [Microsoft エンドポイント データ損失防止を開始する](endpoint-dlp-getting-started.md)
- [Microsoft エンドポイント データ損失防止を使用する](endpoint-dlp-using.md)
- [データ損失防止の概要](data-loss-prevention-policies.md)
- [DLP ポリシーの作成、テスト、調整](create-test-tune-dlp-policy.md)
- [Activity Explorer を使い始める](data-classification-activity-explorer.md)
- [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/)
- [インサイダー リスク管理](insider-risk-management.md)
