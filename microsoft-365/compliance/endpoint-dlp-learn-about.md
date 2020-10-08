---
title: 'Microsoft 365 のエンドポイントのデータ損失防止について学ぶ (プレビュー) '
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
description: 'Microsoft 365 エンドポイントのデータ損失防止は、、ファイルアクティビティを監視し、それらのファイルの保護アクションをエンドポイントに拡張します。 Microsoft 365 のコンプライアンスソリューションでファイルが表示されます '
ms.openlocfilehash: fe4ce05c1f9dd0ebce9a6c3be6fffbecfb36c2af
ms.sourcegitcommit: 5e40c760c1af2a4cc6d85cb782b17f5c979677c5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/07/2020
ms.locfileid: "48379236"
---
# <a name="learn-about-microsoft-365-endpoint-data-loss-prevention-preview"></a>Microsoft 365 のエンドポイントのデータ損失防止について学ぶ (プレビュー) 

Microsoft 365 のデータ損失防止 (DLP) を使用すると、機密があると判断されたアイテムに対して、発生しているアクションを監視し、それらのアイテムの意図しない共有を防ぐことができます。 DLP の詳細については、「[データ損失防止ポリシーの概要](data-loss-prevention-policies.md)」を参照してください。

**エンドポイントデータ損失防止** (エンドポイント DLP) は、Windows 10 デバイスにある機密アイテムについて、DLP のアクティビティの監視と保護機能を拡張します。 デバイスが、 Microsoft 365 コンプライアンス ソリューションに オンボードすると、機密アイテムを使用してユーザーが行っていることに関する情報が[Activity Explorer](data-classification-activity-explorer.md)に表示され、[DLPポリシー](create-test-tune-dlp-policy.md)を通して、それらのアイテムに保護アクションを適用できます。

## <a name="endpoint-activities-you-can-monitor-and-take-action-on"></a>監視と対処が必要なエンドポイントのアクティビティ

Microsoft エンドポイント DLP を使用すると、Windows 10 を実行しているデバイスでユーザーが機密アイテムに行っている次のようなアクティビティを監査および管理できます。　　　 保持されるデータには以下が含まれます。


|アイテムのアクティビティ |監査可能/制限可能  |
|---------|---------|
|作成済み    | 監査可能      |
|名前の変更    |  監査可能       |
|リムーバブルメディアへのコピーと作成     |     監査可能/制限可能|
|\\my-server\fileshare などのネットワーク共有にコピーされます   |     監査可能/制限可能    |
|印刷済み |    監査可能/制限可能       |
|Chromium Edge 経由でクラウドにコピー    |   監査可能/制限可能        |
|許可されていないアプリによってアクセスされました    |  監査可能/制限可能       |

## <a name="whats-different-in-endpoint-dlp"></a>エンドポイント DLP との違い

エンドポイント DLP を掘り下げる前に知っておく必要がある追加の概念がいくつかあります。

### <a name="enabling-device-management"></a>デバイス管理を有効にする

デバイス管理は、デバイスからテレメトリを収集できる機能です。これは、エンドポイント DLP や [インサイダー リスク管理](insider-risk-management.md)などの 365 Microsoft のコンプライアンスソリューションに導入する機能です。 DLP ポリシーの場所として使用するすべてのデバイスをオンボードする必要があります。

![デバイス管理を有効にする](../media/endpoint-dlp-learn-about-1-enable-device-management.png)

オンボードとオフボードは、デバイス管理センターからダウンロードするスクリプトを通して処理されます。 センターには、次の展開方法ごとにカスタムスクリプトがあります：

- ローカルスクリプト (最大10台のマシン)
- グループ ポリシー
- System Center Configuration Manager （ バージョン 1610以降 ）
- Mobile Device Management/Microsoft Intune
- 非永続的マシン用の VDI のオンボードスクリプト

![デバイスオンボーディングページ](../media/endpoint-dlp-learn-about-3-device-onboarding-page.png)

 デバイスをオンボードにするには、[Microsoft 365 エンドポイント DLPの使用を開始する](endpoint-dlp-getting-started.md)の手順を使用します。

[Microsoft Defender Advanced Threat Protection (Microsoft Defender ATP)](https://docs.microsoft.com/windows/security/threat-protection/)を通して、デバイスをオンボーディングしている場合、これらのデバイスは自動的にデバイスの一覧に表示されます。

![デバイスリストを管理する](../media/endpoint-dlp-learn-about-2-device-list.png)

### <a name="viewing-endpoint-dlp-data"></a>エンドポイント DLP データの表示

 エンドポイント DLP は、MIME タイプに基づいてアクティビティを監視するため、ファイル拡張子が変更された場合でもアクティビティがキャプチャされます。 パブリックプレビューでは、すべてが監視されます:

- Word ファイル
- PowerPoint ファイル
- Excel ファイル
- PDF ファイル
- .csv ファイル
- .tsv ファイル
- c ファイル
- クラス ファイル
- cpp ファイル
- cs ファイル
- h ファイル
- java ファイル

> [!NOTE]
> .txt とソースコードのファイルは既定では監査されません。 DLP は、適用されたポリシーに対して DLP を評価し、それに従って、ユーザーのアクションを監査またはブロックします。

デバイスがオンボードされると、場所としてデバイスを使用する DLP ポリシーを構成し、展開する前でも、監査されたアクティビティに関する情報がアクティビティエクスプローラーに流れます。

![アクティビティ エクスプローラーでのエンドポイント dlp イベント](../media/endpoint-dlp-learn-about-4-activity-explorer.png)

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

![usb アクティビティ属性にコピーする](../media/endpoint-dlp-learn-about-5-activity-attributes.png)

## <a name="next-steps"></a>次の手順

ここまでエンドポイント DLP について学びましたので、次のステップの手順は以下になります：

1) [Microsoft Endpoint データ損失防止 (プレビュー) を開始する](endpoint-dlp-getting-started.md)
2) [エンドポイント データ損失防止 (プレビュー) を使用する](endpoint-dlp-using.md)

## <a name="see-also"></a>関連項目

- [Microsoft Endpoint データ損失防止 (プレビュー) を開始する](endpoint-dlp-getting-started.md)
- [エンドポイント データ損失防止 (プレビュー) を使用する](endpoint-dlp-using.md)
- [データ損失防止の概要](data-loss-prevention-policies.md)
- [DLP ポリシーの作成、テスト、調整](create-test-tune-dlp-policy.md)
- [Activity Explorer を使い始める](data-classification-activity-explorer.md)
- [Microsoft Defender Advanced Threat Protection (Microsoft Defender ATP) ](https://docs.microsoft.com/windows/security/threat-protection/)
- [インサイダー リスク管理](insider-risk-management.md)