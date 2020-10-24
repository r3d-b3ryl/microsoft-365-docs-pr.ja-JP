---
title: Contoso Corporation の情報保護
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/02/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Contoso 社が Microsoft 365 の情報保護機能を使用して、クラウド内のデジタルアセットをセキュリティで保護する方法について説明します。
ms.openlocfilehash: a1aa08a20d284d3a003f4a406c37f2107ce19bd1
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754607"
---
# <a name="information-protection-for-the-contoso-corporation"></a>Contoso Corporation の情報保護

Contoso 社は情報セキュリティに関して深刻なものです。製品設計と独自の製造手法を説明する知的財産を漏洩または破壊することによって、競合の不利になります。

機密のデジタル資産をクラウドに移行する前に、Contoso 社は社内の情報の分類と保護要件が、Microsoft 365 for enterprise のクラウドベースのサービスによってサポートされていることを確認しました。

## <a name="contoso-data-security-classification"></a>Contoso データセキュリティの分類

Contoso 社は、データの分析を行い、次の分類レベルを決定しました。

| レベル 1: ベースライン | レベル 2: 機密 | レベル 3: 厳しく規制 |
|:-------|:-----|:-----|
| データは暗号化され、認証されたユーザーのみが使用できます。<BR> <BR> オンプレミスとクラウドベースのストレージおよびワークロードに格納されているすべてのデータに対して提供されます。データは、サービス内に存在し、サービスとクライアントデバイス間で転送される間は暗号化されます。 <BR><BR>レベル 1 のデータの例には、通常のビジネス通信 (電子メール) や、管理、販売、およびサポート ワーカー用のファイルがあります。 | レベル 1 以上の強力な認証とデータ損失保護。<BR> <BR> 強力な認証には、SMS 検証を使用した Azure 多要素認証 (MFA) が含まれています。 データ損失防止は、機密情報または重要な情報が Microsoft クラウドの外部では転送されないようにすることを保証します。<BR><BR>レベル 2 のデータの例には、財務情報や法的情報、新製品の研究開発データがあります。 | レベル 2 以上の最高レベルの暗号化、認証、監査。<BR><BR>保存データおよびクラウド内のデータに対する最高レベルの暗号化。地域の規制に準拠し、スマート カードや詳細な監査と警告を使用する MFA と組み合わされています。<BR> <BR>レベル3のデータの例としては、顧客およびパートナーの個人情報、製品エンジニアリング仕様、独自の製造技術があります。  |
||||

## <a name="contoso-information-policies"></a>Contoso 情報ポリシー
次の表に、Contoso 社の情報ポリシーを示します。


| 値 | Access | データ保存期間 | 情報保護 |
|:-------|:-----|:-----|:-----|
| 低いビジネス価値 (レベル 1: ベースライン) | すべてへのアクセスを許可します。  | 6 か月 | 暗号化を使用します。 |
| 中程度のビジネス価値 (レベル 2: 機密) | Contoso 社の従業員、下請け業者、パートナーにアクセスできるようにします。 <BR><BR> MFA、トランスポート層セキュリティ (TLS)、およびモバイル アプリケーション管理 (MAM) を使用します。 | 2 年  | データ整合性のためにハッシュ値を使用します。  |
| 高度なビジネス価値 (レベル 3: 厳しく規制) | エグゼクティブ、およびエンジニアリングと製造の潜在顧客に対してアクセスを許可します。 <BR> <BR> 管理されたネットワーク デバイスのみの Rights Management System (RMS) です。  | 7 年  | 否認防止のためにデジタル署名を使用します。  |
|||||

## <a name="the-contoso-path-to-information-protection-with-microsoft-365-for-enterprise"></a>Microsoft 365 for enterprise を使用した情報保護への Contoso のパス

Contoso 社は、次の手順に従って、情報保護の要件に応じて Microsoft 365 for enterprise を準備します。

1. 保護する情報を特定する

   Contoso 社は、オンプレミスの SharePoint サイトとファイル共有に配置されている既存のデジタル資産を幅広くレビューし、各資産に分類しました。

2. 各データ レベルについてアクセス、保持、情報保護ポリシーを決定する

   データ レベルに基づいて、Contoso 社は詳細なポリシー要件を決定しました。この要件は、クラウドへの移行時に既存のデジタル資産を保護するために使用されました。

3. さまざまなレベルの情報について、機密ラベルとその設定を作成する

   Contoso 社では、データのレベルに応じた機密ラベルを作成しました。「厳しく規制」のラベルで、暗号化、アクセス許可、透かしなどが含まれます。

4.  オンプレミスの SharePoint サイトとファイル共有から新しい SharePoint サイトにデータを移動する

    新しい SharePoint サイトに移行したファイルには、そのサイトに割り当てられた既定の保持ラベルを継承させました。

5.  従業員に新しいドキュメントの機密ラベルを使用する方法、新しい SharePoint サイトを作成するときに Contoso IT と対話する方法、および常に SharePoint サイトにデジタルアセットを格納する方法を学習します。

    不適切なワーカー情報の変更-ストレージ習慣は、クラウドの情報保護移行の最も難しい部分と見なされることがよくあります。 Contoso IT and management 従業員がデジタルアセットを常にクラウドにラベル付けして保存し、オンプレミスのファイル共有を使用しないで、サードパーティ製のクラウドストレージサービスまたは USB ドライブを使用しないようにする必要があります。

## <a name="conditional-access-policies-for-information-protection"></a>情報保護のための条件付きアクセス ポリシー

Contoso 社は、Exchange Online と SharePoint の展開の一環として、次の条件付きアクセスポリシーのセットを構成し、適切なグループに適用しました。

- [デバイスで管理されるアプリケーション アクセスと管理されないアプリケーション アクセスのポリシー](../security/office-365-security/identity-access-policies.md)
- [Exchange Online アクセス ポリシー](../security/office-365-security/secure-email-recommended-policies.md)
- [SharePoint アクセス ポリシー](../security/office-365-security/sharepoint-file-access-policies.md)

情報保護のための Contoso ポリシーの結果として、次のようなセットが表示されます。

![デバイス、Exchange Online、および SharePoint の条件付きアクセス ポリシー](../media/contoso-info-protect/contoso-info-protect-fig1.png)

>[!Note]
>Contoso 社は、ID とサインイン用に追加の条件付きアクセス ポリシーも構成しました。 「[Contoso 社の ID](contoso-identity.md#conditional-access-policies-for-identity-and-device-access)」を参照してください。
>

これらのポリシーでは、次のことを確実にします。

- 許可されているアプリと、組織のデータによって実行できるアクションは、アプリ保護ポリシーによって定義されます。
- PC とモバイル デバイスが必ず準拠している。
- Exchange Online では、Exchange Online の Office 365 message encryption (OME) を使用します。
- SharePoint では、アプリ強制の制限が使用されます。
- SharePoint は、ブラウザー専用のアクセスにアクセス制御ポリシーを使用して、管理されていないデバイスのアクセスはブロックする。

## <a name="mapping-microsoft-365-for-enterprise-features-to-contoso-data-levels"></a>エンタープライズ機能に関する Microsoft 365 の Contoso データレベルへのマッピング

次の表は、Microsoft 365 for enterprise の情報保護機能への Contoso データレベルのマッピングを示しています。

| レベル | Microsoft 365 クラウドサービス | Windows 10 および Microsoft 365 Apps for enterprise | セキュリティとコンプライアンス |
|:-------|:-----|:-----|:-----|
| レベル 1: ベースライン  | SharePoint および Exchange Online の条件付きアクセス ポリシー <BR> SharePoint サイトのアクセス許可 | 機密ラベル <BR> BitLocker <BR> Windows 情報保護 | デバイスの条件付きアクセス ポリシーとモバイル アプリケーション管理ポリシー |
| レベル 2: 機密 | レベル 1 プラス: <BR> <BR> 秘密度ラベル <BR> SharePoint サイトの Microsoft 365 保持ラベル <BR> SharePoint および Exchange Online 用のデータ損失防止 <BR> 分離した SharePoint サイト  | レベル 1 プラス: <BR> <BR> デジタル資産の機密ラベル  | レベル 1 |
| レベル 3: 厳しく規制 | レベル 2 プラス: <BR><BR> 秘密情報の暗号化と保護を独自のキー (BYOK) にする <BR> Microsoft 365 サービスと対話する基幹業務アプリケーションの Azure キーヴォールト | レベル 2 | レベル 1 |
|||||

結果として得られる Contoso の情報保護構成を次に示します。

![Contoso 社の結果として得られる情報保護構成](../media/contoso-info-protect/contoso-info-protect-fig2.png)

## <a name="next-step"></a>次の手順

Contoso 社が、id およびアクセス管理、脅威保護、情報保護、およびセキュリティ管理のために [Microsoft 365 for enterprise のセキュリティ機能](contoso-security-summary.md) を使用する方法について説明します。

## <a name="see-also"></a>関連項目

[セキュリティのロードマップ](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-roadmap)

[Microsoft 365 for enterprise の概要](microsoft-365-overview.md)

[テスト ラボ ガイド](m365-enterprise-test-lab-guides.md)
