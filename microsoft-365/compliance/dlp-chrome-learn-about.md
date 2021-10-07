---
title: Microsoft Compliance Extension の詳細情報
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
ms.localizationpriority: high
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: Microsoft Compliance Extension は、ファイル アクティビティの監視と制御、および保護措置を Google Chrome ブラウザーに拡張します。
ms.openlocfilehash: ff0df602e68338315becabd0c5b65f981fe4dd43
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60179189"
---
# <a name="learn-about-the-microsoft-compliance-extension"></a>Microsoft Compliance Extension の詳細情報

[エンドポイントデータ損失防止 (エンドポイント DLP)](endpoint-dlp-learn-about.md) は、Windows 10 デバイスにある機密アイテムについて、[Microsoft 365 data loss prevention (DLP)](dlp-learn-about-dlp.md) のアクティビティの監視と保護機能を拡張します。 デバイスが、 Microsoft 365 コンプライアンス ソリューションに オンボードすると、機密アイテムを使用してユーザーが行っていることに関する情報が[Activity Explorer](data-classification-activity-explorer.md)に表示され、[DLPポリシー](create-test-tune-dlp-policy.md)を通して、それらのアイテムに保護アクションを適用できます。

Microsoft Compliance Extension を Windows 10 デバイスにインストールすると、ユーザーが Google Chrome を使用して機密アイテムにアクセスしようとしたり、クラウド サービスにアップロードしようとしたりするのを監視し、DLP によって保護措置を講じることができます。  

## <a name="activities-you-can-monitor-and-take-action-on"></a>監視と対処が必要なアクティビティ

Microsoft Compliance Extension を使用すると、Windows 10 を実行しているデバイスでユーザーが機密アイテムに行っている次のようなアクティビティを監査および管理できます。

アクティビティ |説明  | サポート対象のポリシー アクション|
|---------|---------|---------|
|ファイルがクラウドにコピーされました  | ユーザーが制限されたサービス ドメインに機密アイテムをアップロードしようとした場合、Chrome ブラウザーを介してアイテムにアクセスしようとした場合に検出します |監査、ブロック|
|ファイルが印刷されました  |ユーザーが Chrome ブラウザーで開いている機密性の高いアイテムをローカルまたはネットワークプリンタに印刷しようとした場合に検出します |上書き、ブロックの監査、ブロック|
|ファイルがクリップボードにコピーされました |ユーザーが Chrome ブラウザーで表示中の機密アイテムから情報をコピーし、他のアプリ、プロセス、またはアイテムに貼り付けようとした場合に検出します。 |上書き、ブロックの監査、ブロック|
|ファイルがリムーバブル ストレージにコピーされました    | ユーザーが、機密アイテムや Chrome ブラウザーで開いている機密アイテムの情報をリムーバブルメディアや USB デバイスにコピーしようとした場合に検出します |上書き、ブロックの監査、ブロック|
|ファイルがネットワーク共有にコピーされました  |ユーザーが、機密アイテムやその情報をネットワーク共有やマッピングされたネットワーク ドライブにコピーしようとした場合に検出します。|上書き、ブロックの監査、ブロック |

## <a name="deployment-process"></a>展開プロセス
1. [エンドポイント データ損失防止を開始する](endpoint-dlp-getting-started.md)
2. [Windows 10 デバイスのオンボード ツールと各種方法](dlp-configure-endpoints.md)
3. [Windows 10 デバイスに拡張機能をインストール](dlp-chrome-get-started.md)
4. クラウド サービスへのアップロードや許可されていないブラウザーからのアクセスを制限する [DLP ポリシーを作成または編集](create-test-tune-dlp-policy.md)し、Windows 10 デバイスに適用します。

## <a name="next-steps"></a>次の手順

導入手順とシナリオの詳細については、「[Microsoft Compliance Extension を開始する](dlp-chrome-get-started.md)」を参照してください。

## <a name="see-also"></a>関連項目

- [Microsoft Compliance Extension を開始する](dlp-chrome-get-started.md)
- [Microsoft 365 のエンドポイントのデータ損失防止についての詳細情報](endpoint-dlp-learn-about.md)
- [Microsoft エンドポイント データ損失防止を開始する](endpoint-dlp-getting-started.md)
- [Microsoft エンドポイント データ損失防止を使用する](endpoint-dlp-using.md)
- [データ損失防止について](dlp-learn-about-dlp.md)
- [DLP ポリシーの作成、テスト、調整](create-test-tune-dlp-policy.md)
- [Activity Explorer を使い始める](data-classification-activity-explorer.md)
- [Microsoft Defender for Endpoint](/windows/security/threat-protection/)
- [インサイダー リスク管理](insider-risk-management.md)
