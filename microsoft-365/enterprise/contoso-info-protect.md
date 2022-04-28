---
title: Contoso Corporation の情報保護
author: kelleyvice-msft
f1.keywords:
- NOCSH
ms.author: kvice
manager: scotv
ms.date: 10/02/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Contoso がエンタープライズ向けにMicrosoft 365の情報保護機能を使用して、クラウドでデジタル資産をセキュリティで保護する方法について説明します。
ms.openlocfilehash: eda36fab658a8352289a6245c565e54758fdd87a
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "65092185"
---
# <a name="information-protection-for-the-contoso-corporation"></a>Contoso Corporation の情報保護

Contoso は情報セキュリティについて深刻です。 製品の設計と独自の製造技術を記述する知的財産の漏えいまたは破壊は、競争上の不利な立場に置かれます。

Contoso は、機密性の高いデジタル資産をクラウドに移行する前に、オンプレミスの情報の分類と保護の要件が、企業向けのMicrosoft 365のクラウドベースのサービスによってサポートされていることを確認しました。

## <a name="contoso-data-security-classification"></a>Contoso データ セキュリティの分類

Contoso はデータの分析を実行し、次の分類レベルを決定しました。

| レベル 1: ベースライン | レベル 2: 機密 | レベル 3: 厳しく規制 |
|:-------|:-----|:-----|
| データは暗号化され、認証されたユーザーのみが使用できます。<BR> <BR> オンプレミスとクラウドベースのストレージとワークロードに格納されているすべてのデータに対して提供されます。 データは、サービス内に存在している間、およびサービスとクライアント デバイス間の転送中は暗号化されます。 <BR><BR>レベル 1 のデータの例には、通常のビジネス通信 (電子メール) や、管理、販売、およびサポート ワーカー用のファイルがあります。 | レベル 1 以上の強力な認証とデータ損失保護。<BR> <BR> 強力な認証には、SMS 検証を使用した多要素認証 (MFA) Azure ADが含まれます。 Microsoft Purview データ損失防止により、機密性の高い情報や重要な情報が Microsoft クラウドの外部に移動することが保証されます。<BR><BR>レベル 2 のデータの例には、財務情報や法的情報、新製品の研究開発データがあります。 | レベル 2 以上の最高レベルの暗号化、認証、監査。<BR><BR>保存データおよびクラウド内のデータに対する最高レベルの暗号化。地域の規制に準拠し、スマート カードや詳細な監査と警告を使用する MFA と組み合わされています。<BR> <BR>レベル 3 データの例には、顧客とパートナーの個人情報、製品エンジニアリング仕様、および独自の製造技術があります。  |
||||

## <a name="contoso-information-policies"></a>Contoso の情報ポリシー
次の表に、Contoso 情報ポリシーの一覧を示します。


| 値 | Access | データ保存期間 | 情報保護 |
|:-------|:-----|:-----|:-----|
| 低いビジネス価値 (レベル 1: ベースライン) | All へのアクセスを許可します。  | 6 か月 | 暗号化を使用します。 |
| 中程度のビジネス価値 (レベル 2: 機密) | Contoso の従業員、下請け業者、パートナーへのアクセスを許可します。 <BR><BR> MFA、トランスポート層セキュリティ (TLS)、およびモバイル アプリケーション管理 (MAM) を使用します。 | 2 年  | データ整合性のためにハッシュ値を使用します。  |
| 高度なビジネス価値 (レベル 3: 厳しく規制) | エグゼクティブ、およびエンジニアリングと製造の潜在顧客に対してアクセスを許可します。 <BR> <BR> 管理されたネットワーク デバイスのみの Rights Management System (RMS) です。  | 7 年  | 否認防止のためにデジタル署名を使用します。  |
|||||

## <a name="the-contoso-path-to-information-protection-with-microsoft-365-for-enterprise"></a>エンタープライズ向けのMicrosoft 365を使用した情報保護への Contoso パス

Contoso は、次の手順に従って、情報保護要件のためにエンタープライズ向けのMicrosoft 365を準備しました。

1. 保護する情報を特定する

   Contoso は、オンプレミスのSharePoint サイトとファイル共有にある既存のデジタル資産を広範に確認し、各資産を分類しました。

2. 各データ レベルについてアクセス、保持、情報保護ポリシーを決定する

   データ レベルに基づいて、Contoso 社は詳細なポリシー要件を決定しました。この要件は、クラウドへの移行時に既存のデジタル資産を保護するために使用されました。

3. さまざまなレベルの情報に対する秘密度ラベルとその設定を作成する

   Contoso 社では、データのレベルに応じた機密ラベルを作成しました。「厳しく規制」のラベルで、暗号化、アクセス許可、透かしなどが含まれます。

4. オンプレミスのSharePoint サイトとファイル共有から新しいSharePoint サイトにデータを移動する

    新しい SharePoint サイトに移行したファイルには、そのサイトに割り当てられた既定の保持ラベルを継承させました。

5. 新しいドキュメントに秘密度ラベルを使用する方法、新しいSharePoint サイトを作成するときに Contoso IT と対話する方法、SharePoint サイトにデジタル資産を常に格納する方法を従業員にトレーニングする

    ワーカー情報ストレージの不適切な習慣を変更することは、多くの場合、クラウドの情報保護の移行の最も困難な部分と見なされます。 Contoso IT と経営陣は、従業員が常にデジタル資産にラベルを付けてクラウドに保存し、オンプレミスのファイル共有の使用を控え、サードパーティのクラウド ストレージ サービスや USB ドライブを使用しないようにするために必要でした。

## <a name="conditional-access-policies-for-information-protection"></a>情報保護のための条件付きアクセス ポリシー

Contoso は、Exchange OnlineとSharePointのロールアウトの一環として、次の条件付きアクセス ポリシーのセットを構成し、それらを適切なグループに適用しました。

- [デバイスで管理されるアプリケーション アクセスと管理されないアプリケーション アクセスのポリシー](../security/office-365-security/identity-access-policies.md)
- [Exchange Online アクセス ポリシー](../security/office-365-security/secure-email-recommended-policies.md)
- [SharePoint アクセス ポリシー](../security/office-365-security/sharepoint-file-access-policies.md)

情報保護のための Contoso ポリシーの結果セットを次に示します。

:::image type="content" alt-text="デバイス、Exchange Online、および条件付きアクセス ポリシー SharePoint。" source="../media/contoso-info-protect/contoso-info-protect-fig1.png" lightbox="../media/contoso-info-protect/contoso-info-protect-fig1.png":::

>[!Note]
>Contoso 社は、ID とサインイン用に追加の条件付きアクセス ポリシーも構成しました。 「[Contoso 社の ID](contoso-identity.md#conditional-access-policies-for-zero-trust-identity-and-device-access)」を参照してください。
>

これらのポリシーでは、次のことを確実にします。

- 許可されているアプリと、組織のデータに対して実行できるアクションは、アプリ保護ポリシーによって定義されます。
- PC とモバイル デバイスが必ず準拠している。
- Exchange Onlineでは、Exchange OnlineにOffice 365メッセージ暗号化 (OME) が使用されます。
- SharePointでは、アプリによる制限が使用されます。
- SharePoint は、ブラウザー専用のアクセスにアクセス制御ポリシーを使用して、管理されていないデバイスのアクセスはブロックする。

## <a name="mapping-microsoft-365-for-enterprise-features-to-contoso-data-levels"></a>エンタープライズ機能のMicrosoft 365を Contoso データ レベルにマッピングする

次の表は、エンタープライズ向けのMicrosoft 365の情報保護機能に Contoso データ レベルをマップします。

| レベル | クラウド サービスのMicrosoft 365 | Windows 10 および Microsoft 365 Apps for enterprise | セキュリティとコンプライアンス |
|:-------|:-----|:-----|:-----|
| レベル 1: ベースライン  | SharePoint および Exchange Online の条件付きアクセス ポリシー <BR> SharePoint サイトのアクセス許可 | 機密ラベル <BR> BitLocker <BR> Windows 情報保護 | デバイスの条件付きアクセス ポリシーとモバイル アプリケーション管理ポリシー |
| レベル 2: 機密 | レベル 1 プラス: <BR> <BR> 秘密度ラベル <BR> SharePoint サイトの Microsoft 365 保持ラベル <BR> SharePoint および Exchange Online 用のデータ損失防止 <BR> 分離した SharePoint サイト  | レベル 1 プラス: <BR> <BR> デジタル資産の機密ラベル  | レベル 1 |
| レベル 3: 厳しく規制 | レベル 2 プラス: <BR><BR> 独自のキー (BYOK) 暗号化と営業秘密情報の保護を持ち込む <BR> Microsoft 365 サービスと対話する基幹業務アプリケーションの Azure Key Vault | レベル 2 | レベル 1 |
|||||

結果として得られる Contoso の情報保護構成を次に示します。

:::image type="content" alt-text="Contoso の結果として得られる情報保護の構成。" source="../media/contoso-info-protect/contoso-info-protect-fig2.png":::

## <a name="next-step"></a>次の手順

Contoso が、ID とアクセスの管理、脅威保護、情報保護、[およびセキュリティ管理のために、エンタープライズ向けにMicrosoft 365全体のセキュリティ機能](contoso-security-summary.md)を使用する方法について説明します。

## <a name="see-also"></a>関連項目

[セキュリティ ロードマップ](../security/office-365-security/security-roadmap.md)

[Microsoft 365 for enterprise の概要](microsoft-365-overview.md)

[テスト ラボ ガイド](m365-enterprise-test-lab-guides.md)