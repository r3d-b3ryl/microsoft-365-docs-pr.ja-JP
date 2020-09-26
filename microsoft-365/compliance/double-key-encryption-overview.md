---
title: 二重キー暗号化の概要とよくある FAQ
description: Microsoft 365 の二重キー暗号化についてよく寄せられる質問。
author: kccross
ms.author: krowley
manager: laurawi
ms.date: 09/22/2020
ms.topic: conceptual
ms.service: information-protection
audience: Admin
ms.reviewer: esaggese
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.openlocfilehash: 98c61e66155e21624e8ecba460ebc3041e72ada5
ms.sourcegitcommit: 1423e08a02d30f0a2b993fb99325c3f499c31787
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/25/2020
ms.locfileid: "48277656"
---
# <a name="double-key-encryption-frequently-asked-questions"></a>二重キー暗号化についてよく寄せられる質問

二重キー暗号化のしくみについての質問がありますか。 ここで回答を確認してください。

## <a name="what-is-double-key-encryption-for-microsoft-365-dke"></a>Microsoft 365 (DKE) の二重キー暗号化とは

Microsoft 365 の二重キー暗号化により、お客様は、特殊な要件を満たすように機密性の高いデータを保護することができます。 お客様は、暗号化キーのフルコントロールを維持することができます。 2つのキーを使用してデータを保護します。コントロール内の1つのキーと、Microsoft Azure に安全に格納されている2番目のキー。 2つのキー暗号化で保護されたデータを表示するには、両方のキーにアクセスする必要があります。 Microsoft は、これらのキーのいずれか1つにしかアクセスできないため、保護されたデータは Microsoft からはアクセスできないままになり、データのプライバシーとセキュリティを完全に制御できるようになります。  

キーの要求に使用する Double キー暗号化サービスは、任意の場所 (オンプレミスのキー管理サーバーまたはクラウド) にホストできます。 他のアプリケーションと同様にサービスを維持します。 二重キー暗号化を使用すると、二重キー暗号化サービスへのアクセスを制御できます。 非常に機密性の高いデータを社内に保存したり、クラウドに移動したりすることができます。 キーのフルコントロールを維持しているため、サードパーティからのアクセスを禁止することができます。 [Double キー暗号化] を使用すると、データとキーを同じ場所に格納できます。

DKE は、一般的なデータ保護規則 (GDPR)、医療保険の携行性と責任に関する法律 (HIPAA)、グラムリーチブライ Act (GLBA)、ロシアのデータローカリゼーション法律 (連邦法) など、いくつかの規制および基準における規制要件を満たすのに役立つ情報を示します。 242-FZ、オーストラリアの連邦プライバシー法1988、ニュージーランドのプライバシー法1993。

## <a name="can-i-use-double-key-encryption-with-microsoft-office-built-in-sensitivity-labeling"></a>Microsoft Office の組み込みの機密ラベルで、二重のキー暗号化を使用することはできますか?

Azure Information Protection ユニファイドラベルクライアントを使用して、2重のキー暗号化でドキュメントを保護する必要があります。 現時点では、Microsoft Office の組み込みの機密ラベルを使用することはできません。 

## <a name="what-microsoft-365-apps-can-i-use-with-dke"></a>DKE ではどのような Microsoft 365 アプリを使用できますか?

DKE ラベルを使用すると、Windows のデスクトップ版の Word、Excel、および PowerPoint を使用してドキュメントを保護することができます。 Windows で * 12711 以降 (デスクトップ版の Word、PowerPoint、Excel) を使用していることを確認してください。

## <a name="how-is-double-key-encryption-different-from-the-existing-hold-your-own-key-hyok-solution"></a>既存のキー (HYOK) ソリューションとは異なる二重キー暗号化と既存のキーの違い

二重キー暗号化は、2つのキーでデータを暗号化します。 暗号化キーはコントロール内にあり、2番目のキーは Microsoft Azure に格納されているため、暗号化されたデータをクラウドに移行できます。 HYOK は、1つのキーでコンテンツを保護し、キーは常にオンプレミスで保護されます。  

## <a name="can-double-key-encrypted-documents-be-shared-externally"></a>二重の重要な暗号化ドキュメントは外部で共有できますか?

2つの暗号化されたドキュメントを、ユーザーとは別のテナントのユーザーと共有することができます。

- 二重キー暗号化サービスのキーにアクセスするために必要なアクセス許可があること。

- Microsoft Azure のキーにアクセスするために必要なアクセス許可が付与されている。

## <a name="what-happens-to-documents-that-are-protected-with-hyok"></a>HYOK で保護されているドキュメントの処理

二重キー暗号化の展開は、既存の HYOK セットアップには影響しません。 ただし、HYOK と並行して二重キー暗号化の使用を開始することをお勧めします。

## <a name="can-i-run-double-key-encryption-in-my-non-microsoft-air-gapped-environment"></a>Microsoft 以外の gapped 環境で、二重のキー暗号化を実行できますか。

DKE は、Microsoft Azure へのアクセスを必要とするため、これらの環境をサポートしていません。

## <a name="where-can-i-store-double-key-encrypted-documents"></a>二重キーで暗号化されたドキュメントはどこに保存できますか?

二重キーで暗号化されたドキュメントを社内またはクラウドに保存することができます。 クラウドでは、暗号化されたコンテンツを SharePoint Online と OneDrive for business に移動できます。 Microsoft は秘密キーへのアクセス権を持っていないため、暗号化されたデータは Microsoft に対して非透過の状態になります。 これは、Office Web Apps で暗号化されたドキュメントをオンラインで表示できないことも意味します。

## <a name="what-regions-and-languages-is-double-key-encryption-available-in-is-double-key-encryption-available-worldwide"></a>二重キー暗号化が使用可能な地域と言語 世界中で2重のキー暗号化を利用できますか?

DKE ラベルは、Microsoft Information Protection の他の機密ラベルと同じ言語にローカライズされます。 世界中で使用できる二重キー暗号化があります。

## <a name="can-i-convert-a-non-dke-label-to-a-dke-label"></a>非 DKE ラベルを DKE ラベルに変換することはできますか。

いいえ。 作成後に DKE をラベルに追加することはできません。 代わりに、[キーの **暗号化を使用** する] を選択し、ラベルの作成時に二重キー暗号化サービスの URL を指定する必要があります。

## <a name="how-do-i-roll-my-dke-keys"></a>DKE キーをロールするにはどうすればよいですか?

Azure に格納するロール (循環またはキー更新とも呼ばれます) の手順については、「 [Azure Information Protection のテナントキーの操作](https://docs.microsoft.com/azure/information-protection/operations-customer-managed-tenant-key)」を参照してください。

DKE サービスの新しいキーを作成する方法については、「 [テナントとキーの設定](double-key-encryption.md#tenant-and-key-settings) 」を参照してください。

キーを作成するときに、名前と GUID を設定します。 キーを回転させると、名前と GUID を持つ古いレコードが保持されますが、同じ名前で GUID が異なる新しいレコードが追加されます。 新しいキーがアクティブとして設定され、公開キー API が新しい暗号化に対してそのキーを返し始めます。 両方のキーを復号化に使用して、新しいコンテンツと古いコンテンツを復号化できるようにします。
