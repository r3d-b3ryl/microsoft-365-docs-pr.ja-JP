---
title: カリフォルニア州消費者プライバシー法 (CCPA)
description: Microsoft サービスとカリフォルニアのコンシューマプライバシー法 (CCPA)。
keywords: Microsoft 365、コンプライアンス、サービス
localization_priority: None
ms.prod: Microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: M365-security-compliance
hideEdit: true
titleSuffix: Microsoft Compliance
ms.openlocfilehash: de9fcad3b1d54247114974ce4432068c136fdb2a
ms.sourcegitcommit: b6ab845d64e2801051d249de09ad5059809b649a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42222029"
---
# <a name="california-consumer-privacy-act-ccpa"></a>カリフォルニア州消費者プライバシー法 (CCPA)

## <a name="ccpa-overview"></a>CCPA の概要

カリフォルニアのコンシューマ Privacy 法 (CCPA) は、米国の最初の包括的なプライバシー法です。 カリフォルニアのコンシューマーにさまざまなプライバシー権限を与えます。  CCPA によって制限される企業には、開示、一般的なデータ保護規則 (GDPR) (コンシューマーデータのサブジェクト権限 (DSRs) など)、特定のデータ転送用の「オプトアウト」、「オプトイン」など、これらのコンシューマーにさまざまな義務があります。未成年者の要件。

CCPA は、以下の1つまたは複数のことを満たしているカリフォルニア州の企業にのみ適用されます。 (1) $2500万よりも高い年間売上を得ることができます。または、(2) カリフォルニアの消費者個人の売上から年間収益の50% を超えないようにします。情報、または (3) 5万を超えるカリフォルニア消費者の個人情報を売買または共有します。

CCPA は 2020 年 1 月 1 日から有効になります。 ただし、カリフォルニア弁護士の一般 (AG) による執行は、2020年7月1日に開始されます。

カリフォルニア AG は、CCPA を強制し、非準拠の罰金を発行するためにパワーを与えます。 CCPA は、データ侵害に制限されるアクションのプライベート権限も提供します。 私的権利の行使では、1 つのインシデントの損害は、消費者 1 人当たり $100 から $750 です。 カリフォルニア AG でも CCPA をそのまま適用し、違反ごとに $2,500 以下の罰則金を科しています。また、意図的な違反には $7,500 以下の罰則金を科しています。

## <a name="microsoft-and-the-ccpa"></a>Microsoft と CCPA

カリフォルニアでビジネスを行っている商用のお客様のために、Microsoft は、オンラインサービスとプロフェッショナルサービスの提供に関して、「サービスプロバイダー」としての役割を果たします。  オンラインサービス使用条件 (OST) と Microsoft プロフェッショナルサービスデータ保護補遺 (MSDPA) の条項は、既に CCPA の下のサービスプロバイダーの要件を満たしており、一般にお客様がデータを引き続き転送できるように十分です。オンラインサービスに接続します。 そのため、お客様が Microsoft を CCPA の下のサービスプロバイダーとして利用できるようにするために、追加の契約変更は不要です。

OST で設定されているように、Microsoft は、オンラインサービスのプロビジョニングに適用できるすべての法律および規制に準拠しています。これには、CCPA が含まれます。  

## <a name="microsoft-in-scope-cloud-services"></a>対象となる Microsoft のクラウド サービス

- [Azure](https://aka.ms/AzureCompliance)
- Azure Dev Ops
- [Dynamics 365](https://aka.ms/d365-compliance-list)
- Intune
- [Office 365](https://aka.ms/o365-compliance-framework)
- サポートおよびプロフェッショナルサービス
- Visual Studio

## <a name="how-you-can-prepare-for-your-ccpa-compliance-when-using-microsoft-products-and-services"></a>Microsoft 製品およびサービスを使用する際に CCPA 準拠を準備する方法

CCPA の準備をするために必要ないくつかの手順を以下に示します。

- CCPA プライバシープログラムの一環として、[コンプライアンススコア](compliance-score.md)の GDPR 評価の活用を開始します。
- データ主体要求ツールを使用して、データ主体のアクセス要求 (DSARs) に効率よく応答するためのプロセスを確立します。
- ラベルとポリシーを設定し、Microsoft Information Protection を使用して機密データを検索、分類、保護します。
- メールの暗号化機能を使用して、機密情報をさらに管理します。

## <a name="frequently-asked-questions"></a>よく寄せられる質問

**CCPA によって私の会社はどのような影響を受けますか?**

Californians に対して提供されている CCPA の権限の多くは、GDPR が提供する権限に似ています。これには、アクセス、削除、移植性などの、開示およびデータ主体の権利 (DSR) 要求が含まれます。 そのため、お客様は既存の GDPR ソリューションを参照して、CCPA 準拠に役立てることができます。

CCPA の旅を開始するには、情報の検出に重点を置き、個人情報の共有方法、使用方法、保護方法、および正式なデータ違反の応答プログラムを作成する方法を決定する必要があります。

**GDPR と CCPA の違いは何ですか?**

さまざまな違いがあります。 次のような類似点があります。

- 透明性/暴露義務、
- データのコピーに対するアクセス、削除、および受信のためのコンシューマー権限
- GDPR が同様の契約上の責務を使用して ' プロセッサ ' を定義する方法に似た ' サービスプロバイダ ' の定義。
- ' Controllers ' の GDPR 定義を含む ' ビジネス ' の定義。

CCPA の最大の違いは、データの販売からのオプトアウトをサードパーティに対して有効にするための中心となる要件です (重要な考慮をするためにデータを共有するように定義された「販売」が広く使用されています)。

**CCPA で企業が認めなければならない権利は何ですか?**

CCPA には、次のように、個人情報を収集、転送、販売する規制された企業が必要です。

- 情報を収集する前に、消費者に対して、収集する情報のカテゴリや目的を開示する。
- 収集される個人情報のソース、ビジネス目的、およびカテゴリに関する詳細な開示情報を提供します。これらのカテゴリをどのように販売または他のエンティティに転送するかについても説明します。
- ユーザーが収集した個人情報の特定の部分について、アクセス、削除、および移植性の DSR 権限を有効にします。
- コンシューマーのデータの販売を中止することができるようにするコントロールを有効にします。 ただし、サービスプロバイダーなどの免税エンティティへの転送が許可されます。
- 未成年者の場合、16では、選択プロセスを有効にして、重要な個人情報が販売に積極的にオプトインされずに発生することがないようにします。
- CCPA の消費者の権利に基づき、消費者がその権利の行使によって、差別されないことを確認する。

**CCPA は子供にはどのように適用されますか?**

- CCPA は、13 歳未満の子供に対して、児童オンラインプライバシー保護法 (COPPA) と一致する、保護者による同意の義務を導入しています。
- 16歳から16歳の子供の場合、CCPA は子からオプトイン同意を得るための新しい責務を課しています。

## <a name="use-microsoft-compliance-score-to-assess-your-risk"></a>Microsoft コンプライアンス スコアを使用してリスクを評価する

[Microsoft コンプライアンス スコア](compliance-score.md)は、[ Microsoft 365 コンプライアンス センター](microsoft-365-compliance-center.md)のプレビュー機能で、組織のコンプライアンスの状況を把握し、リスクを軽減するための処置を実行できるようにします。 [コンプライアンススコアを設定](compliance-score-setup.md)した後、[**テンプレート**] ドロップダウンメニューから事前に構成された[ccpa テンプレート](https://go.microsoft.com/fwlink/?linkid=2118004)を選択して、組織がこの規制の要件を満たすことができるようにします。

## <a name="resources"></a>リソース

- [新しいカリフォルニア消費者プライバシー法の準備に役立つ5つのヒント](https://aka.ms/M365ComplianceBlog_RSA)
- [CCPA ガイドの概要](https://info.microsoft.com/ww-landing-Five-tips-to-help-you-prepare-for-the-California-Consumer-Privacy-Act.html)
- [データ主体要求と GDPR](gdpr-data-subject-requests.md)
- [カリフォルニア州消費者プライバシー法 (CCPA) の FAQ](ccpa-faq.md)
- [Microsoft Trust Center のコンプライアンス](https://www.microsoft.com/trust-center/compliance/compliance-overview)
