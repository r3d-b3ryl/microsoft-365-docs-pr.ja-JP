---
title: ダブル キー暗号化の概要と FAQ
description: ダブル キー暗号化に関してよく寄せられる質問。
author: kccross
ms.author: krowley
manager: laurawi
ms.date: 02/28/2022
ms.topic: conceptual
ms.service: information-protection
audience: Admin
ms.reviewer: esaggese
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
ms.openlocfilehash: c42104ccb74aba71b143d1ee31b0ed5893d9396f
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2022
ms.locfileid: "66641836"
---
# <a name="double-key-encryption-frequently-asked-questions"></a>ダブル キー暗号化に関してよく寄せられる質問

ダブル キー暗号化のしくみについて質問がありますか? ここで回答をご覧ください。

## <a name="what-is-double-key-encryption-dke"></a>ダブル キー暗号化 (DKE) とは

Double Key Encryption を使用すると、お客様は機密性の高いデータを保護し、特殊な要件を満たすことができます。 暗号化キーの完全な制御を維持するのに役立ちます。 2 つのキーを使用してデータを保護します。コントロール内の 1 つのキーと、Microsoft Azure に安全に格納されている 2 つ目のキー。 二重キー暗号化で保護されたデータを表示するには、両方のキーにアクセスする必要があります。 Microsoft はこれらのキーの 1 つだけにアクセスできるため、保護されたデータは Microsoft からアクセスできないため、データのプライバシーとセキュリティを完全に制御できます。  

任意の場所 (オンプレミスのキー管理サーバーまたはクラウド) で、キーを要求するために使用される Double Key Encryption サービスをホストできます。 他のアプリケーションと同様にサービスを維持します。 Double Key Encryption を使用すると、Double Key Encryption サービスへのアクセスを制御できます。 機密性の高いデータをオンプレミスに格納することも、クラウドに移動することもできます。 キーの完全な制御を維持しているため、サード パーティのアクセスを防ぐことに自信を持つことができます。 Double Key Encryption を使用すると、データとキーを同じ場所に格納できます。

DKE は、一般的なデータ保護規則 (GDPR)、医療保険の可搬性と説明責任に関する法律 (HIPAA)、Gramm-Balancer-Bliley Act (GLBA)、ロシアのデータローカライズ法 – 連邦法番号など、いくつかの規制や基準にわたる規制要件を満たすのに役立ちます。 242-FZ、オーストラリア連邦プライバシー法 1988、ニュージーランドのプライバシー法 1993。

## <a name="can-i-use-double-key-encryption-with-microsoft-office-built-in-sensitivity-labeling"></a>Microsoft Office 組み込みの秘密度ラベル付けで Double Key Encryption を使用できますか?

ダブル キー暗号化を使用してドキュメントを保護するには、Azure Information Protection統合ラベル付けクライアントを使用する必要があります。 現時点では、Microsoft Office の組み込みの秘密度ラベル付けを使用することはできません。

## <a name="what-microsoft-365-apps-can-i-use-with-dke"></a>DKE で使用できるMicrosoft 365 Appsは何ですか?

Windows 上のデスクトップ バージョンの Word、Excel、PowerPoint を使用して、DKE ラベルを使用してドキュメントを保護できます。 Windows で *.12711 以降 (デスクトップ バージョンの Word、PowerPoint、Excel) を使用していることを確認します。

## <a name="how-is-double-key-encryption-different-from-the-existing-hold-your-own-key-hyok-solution"></a>Double Key Encryption は、既存のホールド独自のキー (HYOK) ソリューションとどのように異なりますか?

Double Key Encryption は、2 つのキーを使用してデータを暗号化します。 暗号化キーは制御下にあり、2 つ目のキーは Microsoft Azure に格納されるため、暗号化されたデータをクラウドに移動できます。 HYOK は 1 つのキーだけでコンテンツを保護し、キーは常にオンプレミスにあります。  

## <a name="can-double-key-encrypted-documents-be-shared-externally"></a>Double Key Encrypted ドキュメントを外部で共有できますか?

Double Key Encrypted ドキュメントは、次のユーザーに限り、別のテナントのユーザーと共有できます。

- Double Key Encryption サービスでキーにアクセスするために必要なアクセス許可を持っています。

- Microsoft Azure でキーにアクセスするために必要なアクセス許可を持っています。

## <a name="what-happens-to-documents-that-are-protected-with-hyok"></a>HYOK で保護されているドキュメントはどうなりますか?

ダブル キー暗号化を展開しても、既存の HYOK 設定には影響しません。 ただし、HYOK と並行してダブル キー暗号化の使用を開始することをお勧めします。

## <a name="can-i-run-double-key-encryption-in-my-non-microsoft-air-gapped-environment"></a>Microsoft 以外の air-gapped 環境で Double Key Encryption を実行できますか?

サービスには Microsoft Azure へのアクセスが必要であるため、DKE ではこれらの環境はサポートされません。

## <a name="where-can-i-store-double-key-encrypted-documents"></a>Double Key Encrypted ドキュメントはどこに保存できますか?

Double Key Encrypted ドキュメントは、オンプレミスまたはクラウドに格納できます。 クラウドでは、暗号化されたコンテンツを SharePoint Online および OneDrive for Businessに移動できます。 Microsoft は秘密キーにアクセスできないため、暗号化されたデータは Microsoft に対して不透明なままです。 これは、Office Web Appsで暗号化されたドキュメントをオンラインで表示できないことも意味します。

## <a name="what-regions-and-languages-is-double-key-encryption-available-in-is-double-key-encryption-available-worldwide"></a>ダブル キー暗号化はどのリージョンと言語で使用できますか? ダブル キー暗号化は世界中で使用できますか?

DKE ラベルは、Microsoft Purview 情報保護の他の秘密度ラベルと同じ言語にローカライズされます。 ダブル キー暗号化は世界中で利用できます。

## <a name="can-i-convert-a-non-dke-label-to-a-dke-label"></a>DKE 以外のラベルを DKE ラベルに変換できますか?

いいえ。 DKE を作成した後は、ラベルに DKE を追加できません。 代わりに、[ **二重キー暗号化の使用** ] を選択し、ラベルを作成するときに Double Key Encryption サービスの URL を指定する必要があります。

## <a name="how-do-i-roll-my-dke-keys"></a>DKE キー操作方法ロールしますか?

Azure に格納するキーのローリング (ローテーションまたはキー再生成とも呼ばれます) の手順については、「Azure [Information Protection テナント キーの操作](/azure/information-protection/operations-customer-managed-tenant-key)」を参照してください。

DKE サービスの新しいキーの作成については、「 [テナントと](double-key-encryption.md#tenant-and-key-settings) キーの設定」を参照してください。

キーを作成するときに、名前と GUID を設定します。 次に、キーをローテーションする場合は、名前と GUID を持つ古いレコードを保持しますが、同じ名前で異なる GUID を持つ新しいレコードを追加します。 公開キー API が新しい暗号化のためにそのキーの返しを開始するように、新しいキーはアクティブとして設定されます。 新しいコンテンツと古いコンテンツを復号化できるように、両方のキーを復号化できます。
