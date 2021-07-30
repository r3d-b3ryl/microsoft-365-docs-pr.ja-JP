---
title: Microsoft 365 のデータ損失防止のオンプレミス スキャナーについての詳細情報
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
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: Microsoft 365 データ損失防止オンプレミス スキャナーは、ファイル アクティビティの監視とそれらのファイルの保護アクションを、オンプレミスのファイル共有と SharePoin tフォルダーおよびドキュメント ライブラリに拡張します。 ファイルは、Azure Information Protection (AIP) スキャナーによってスキャンおよび保護されます
ms.openlocfilehash: c59c6b90f6c219528cbff8a4aadc6472a48ecd23
ms.sourcegitcommit: d817a3aecb700f7227a05cd165ffa7dbad67b09d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/29/2021
ms.locfileid: "53657389"
---
# <a name="learn-about-the-microsoft-365-data-loss-prevention-on-premises-scanner"></a>Microsoft 365 のエンドポイントのデータ損失防止について説明します

Microsoft Data Loss Prevention (オンプレミス スキャナー) は、Microsoft 365 サービス全体で機密アイテムを検出して保護する Microsoft 365 Data Loss Prevention (DLP) スイートの機能の一部です。 MicrosoftのすべてのDLP製品の詳細については、「[データ損失防止の概要](dlp-learn-about-dlp.md)」を参照してください。

**DLP オンプレミス スキャナー** は、ファイル共有と SharePoint ドキュメント ライブラリおよびフォルダー内のオンプレミスの保存データをクロールして、漏洩した場合に組織にリスクをもたらしたり、コンプライアンス ポリシー違反のリスクをもたらしたりする機密アイテムを探します。 これにより、機密性の高いアイテムが適切に使用および保護されていることを確認し、危険にさらされる可能性のある動作を防止するために必要な可視性と制御を得ることができます。 DLP オンプレミス スキャナーは、[組み込み](sensitive-information-type-entity-definitions.md)または[カスタムの機密情報](create-a-custom-sensitive-information-type.md)タイプ、[機密ラベル](sensitivity-labels.md)、またはファイル プロパティを使用して機密情報を検出します。 機密アイテムを使用してユーザーが行っていることに関する情報が[Activity Explorer](data-classification-activity-explorer.md)に表示され、[DLPポリシー](create-test-tune-dlp-policy.md)を通して、それらのアイテムに保護アクションを適用できます。

## <a name="the-dlp-on-premises-scanner-relies-on-azure-information-protection-scanner"></a>DLP オンプレミス スキャナーは Azure Information Protection スキャナーに依存しています

DLP オンプレミス スキャナーは、Azure Information Protection (AIP) スキャナーの完全な実装に依存して、機密性の高いアイテムを監視、ラベル付け、保護します。 AIP スキャナーに慣れていない場合は、AIP スキャナーに慣れておくことを強くお勧めします。 次の記事を参照してください。

- [Azure Information Protection とは](/azure/information-protection/what-is-information-protection)
- [Azure Information Protection 統合ラベル付けスキャナーとは](/azure/information-protection/deploy-aip-scanner)
- [Azure Information Protection 統合ラベリング スキャナーをインストールおよび展開するための要件](/azure/information-protection/deploy-aip-scanner-prereqs)
- [チュートリアル: Azure Information Protection (AIP) 統合ラベル付けスキャナーのインストール](/azure/information-protection/tutorial-install-scanner)
- [Azure Information Protection 統合ラベル付けスキャナーの構成とインストール](/azure/information-protection/deploy-aip-scanner-configure-install)
- [Azure Information Protection 統合されたラベル付けクライアント - バージョンのリリース履歴とサポート ポリシー](/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history)

## <a name="dlp-on-premises-scanner-actions"></a>DLP オンプレミス スキャナーのアクション

DLP オンプレミス スキャナーは、次の 4 つの方法のいずれかを使用してファイルを検出します。

- 機密情報の種類
- 機密度ラベル
- ファイル拡張子
- Office ファイルのみのカスタム ドキュメント プロパティ 

検出されたファイルがリークまたはコンプライアンス ポリシー違反の場合に潜在的なリスクをもたらす場合、DLP オンプレミス スキャナーはこれらの4つのアクションのいずれかを実行できます。

|アクション |説明  |
|---------|---------|
|**これらの人々がオンプレミス スキャナーに保存されているファイルにアクセスするのをブロックします - 全員** | 適用されると、このアクションは、コンテンツ所有者、アイテムを変更した最後のアカウント、および管理者を除くすべてのアカウントへのアクセスをブロックします。 これは、ファイル所有者、リポジトリ所有者 ([[コンテンツ スキャン ジョブのリポジトリ所有者設定の設定]](/azure/information-protection/deploy-aip-scanner-configure-install#use-a-data-loss-prevention-dlp-policy-public-preview) で設定)、最後の修飾子 (SharePoint でのみ識別可能)、および管理者を除く、ファイルレベルで NTFS/SharePoint アクセス許可からすべてのアカウントを削除することによって行われます。 スキャナー アカウントには、ファイルに対する FC 権限も付与されます。|
|**これらの人々がオンプレミス スキャナーに保存されているファイルにアクセスするのをブロックします - 組織全体の (パブリック) アクセスをブロック**    |このアクションを実行すると、**_Everyone_*_、_*_NT AUTHORITY\authentication users_*_、および_*_Domain Users_** SIDがファイルアクセス制御リスト (ACL) から削除されます。 ファイルまたは親フォルダへの権限が明示的に付与されているユーザーとグループのみがファイルにアクセスできます。|
|**ファイルに権限を設定する**|適用されると、このアクションはファイルにその親フォルダーのアクセス許可を継承させます。 デフォルトでは、このアクションは、親フォルダーのアクセス許可が、ファイルに既に存在するアクセス許可よりも制限されている場合にのみ適用されます。 たとえば、ファイルの ACL が **_特定のユーザー_*_のみを許可するように設定されており、親フォルダーが_*_Domain Users_*_グループを許可するように構成されている場合、親フォルダーのアクセス許可はファイルに継承されません。* 親のアクセス許可の制限が緩い場合でも、[継承]を選択すると、この動作を上書きできます**。|
|**不適切な場所からファイルを削除する**|強制されると、このアクションは元のファイルを .txt 拡張子の付いたスタブ ファイルに置き換え、元のファイルのコピーを検疫フォルダーに配置します。 

## <a name="whats-different-in-the-on-premises-scanner"></a>オンプレミス スキャナーの違い

オンプレミス スキャナーを掘り下げる前に知っておく必要のあるいくつかの追加の概念があります。

### <a name="aip-repositories-and-content-scan-jobs"></a>AIP リポジトリとコンテンツ スキャン ジョブ

AIP コンテンツ スキャン ジョブを作成し、DLP エンジンで評価するファイルをホストするリポジトリを特定する必要があります。 作成した AIP コンテンツ スキャン ジョブで DLP ルールが有効になっていることを確認してください。

### <a name="policy-tips"></a>ポリシー ヒント

[ポリシー ヒント](use-notifications-and-policy-tips.md)は、オンプレミス スキャナーでは利用できません。


### <a name="viewing-dlp-on-premises-scanner-events"></a>DLP オンプレミス スキャナー イベントの表示

DLP オンプレミス スキャナー データは、M365 コンプライアンス センター [アクティビティ エクスプローラー](data-classification-activity-explorer.md)で表示します。 

## <a name="next-steps"></a>次のステップ

ここまで DLP オンプレミス スキャナーについて学びましたので、次のステップは以下になります:

1. [DLP オンプレミス スキャナーの使用を開始する](dlp-on-premises-scanner-get-started.md)
2. [DLP オンプレミス スキャナーを使用する](dlp-on-premises-scanner-use.md)

## <a name="see-also"></a>関連項目

- [Getting started with the Microsoft data loss prevention on-premises scanner (Microsoft データ損失防止オンプレミス スキャナーの使用を開始する)](dlp-on-premises-scanner-get-started.md)
- [Use the Microsoft data loss prevention on-premises scanner (Microsoft データ損失防止オンプレミス スキャナーを使用する)](dlp-on-premises-scanner-use.md)
- [データ損失防止について](dlp-learn-about-dlp.md)
- [DLP ポリシーの作成、テスト、調整](create-test-tune-dlp-policy.md)
- [Activity Explorer を使い始める](data-classification-activity-explorer.md)