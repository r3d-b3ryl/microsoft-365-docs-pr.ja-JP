---
title: ダブル キー暗号化の概要と FAQ
description: 2 つのキーの暗号化に関するよく寄せられる質問は、Microsoft 365。
author: kccross
ms.author: krowley
manager: laurawi
ms.date: 12/11/2020
ms.topic: conceptual
ms.service: information-protection
audience: Admin
ms.reviewer: esaggese
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.openlocfilehash: ed07361f8c433a318342ae3c8ad750549992c285
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59212664"
---
# <a name="double-key-encryption-frequently-asked-questions"></a>二重キー暗号化に関するよく寄せられる質問

ダブル キー暗号化の仕組みについて質問がありますか? ここで答えを確認してください。

## <a name="what-is-double-key-encryption-for-microsoft-365-dke"></a>DKE (DKE) のMicrosoft 365キー暗号化とは

Double Key Encryption for Microsoft 365、お客様は機密性の高いデータを保護して、特別な要件を満たします。 これにより、お客様は暗号化キーの完全な制御を維持できます。 2 つのキーを使用してデータを保護します。コントロール内の 1 つのキーと、コントロール内に安全に格納された 2 番目Microsoft Azure。 ダブル キー暗号化で保護されたデータを表示するには、両方のキーにアクセスする必要があります。 Microsoft ではこれらのキーの 1 つしかアクセスできないので、保護されたデータは Microsoft にアクセスできなくなり、データのプライバシーとセキュリティを完全に制御できます。  

選択した場所 (オンプレミスのキー管理サーバーまたはクラウド内) で、キーを要求するために使用する Double Key Encryption サービスをホストできます。 他のアプリケーションと同じ方法でサービスを維持します。 ダブル キー暗号化を使用すると、ダブル キー暗号化サービスへのアクセスを制御できます。 機密性の高いデータは、オンプレミスに保存するか、クラウドに移動できます。 キーの完全な制御を維持するために、サード パーティ製のアクセスを防ぐことに自信を持って取り組む必要があります。 ダブル キー暗号化を使用すると、データとキーを同じ場所に格納できます。

DKE は、一般データ保護規則 (GDPR)、健康保険の移植性および説明責任法 (HIPAA)、Gramm-Leach-Bliley 法 (GLBA)、ロシアのデータローカライズ法 - 連邦法番号など、いくつかの規制および基準に関する規制要件を満たすのに役立ちます。 242-FZ、オーストラリアの連邦プライバシー法 1988、およびニュージーランドのプライバシー法 1993。

## <a name="can-i-use-double-key-encryption-with-microsoft-office-built-in-sensitivity-labeling"></a>組み込みの感度ラベル付Microsoft Office二重キー暗号化を使用できますか?

Azure Information Protection 統合ラベル付けクライアントを使用して、ダブル キー暗号化を使用してドキュメントを保護する必要があります。 現在、組み込みのMicrosoft Officeラベルを使用することはできません。

## <a name="what-microsoft-365-apps-can-i-use-with-dke"></a>DKE Microsoft 365 Apps使用できる機能は何ですか?

DKE ラベルを使用すると、デスクトップ バージョンの Word、Excel、および PowerPointを使用Windows。 オンラインで *.12711 以降 (デスクトップ バージョンの Word、PowerPoint、Excel) を使用Windows。

## <a name="how-is-double-key-encryption-different-from-the-existing-hold-your-own-key-hyok-solution"></a>ダブル キー暗号化と既存のホールド 独自のキー (HYOK) ソリューションの違い

ダブル キー暗号化は、2 つのキーを使用してデータを暗号化します。 暗号化キーはコントロールに格納され、2 番目のキーは Microsoft Azureに格納され、暗号化されたデータをクラウドに移動できます。 HYOK は 1 つのキーでのみコンテンツを保護し、キーは常にオンプレミスにあります。  

## <a name="can-double-key-encrypted-documents-be-shared-externally"></a>Double Key Encrypted documents を外部で共有できますか?

Double Key Encrypted documents は、次のユーザーである限り、別のテナントのユーザーと共有できます。

- ダブル キー暗号化サービスでキーにアクセスするために必要なアクセス許可を持つ。

- キーにアクセスするために必要なアクセス許可を持Microsoft Azure。

## <a name="what-happens-to-documents-that-are-protected-with-hyok"></a>HYOK で保護されているドキュメントは何が起こりますか?

ダブル キー暗号化を展開しても、既存の HYOK セットアップには影響しません。 ただし、HYOK と並行してダブル キー暗号化の使用を開始することをお勧めします。

## <a name="can-i-run-double-key-encryption-in-my-non-microsoft-air-gapped-environment"></a>Microsoft 以外の空きモード環境でダブル キー暗号化を実行できますか?

DKE は、サービスがこれらの環境にアクセスする必要Microsoft Azure。

## <a name="where-can-i-store-double-key-encrypted-documents"></a>Double Key Encrypted ドキュメントはどこに保存できますか?

Double Key Encrypted ドキュメントは、オンプレミスまたはクラウドに保存できます。 クラウドでは、暗号化されたコンテンツを [オンライン] および [SharePoint] にOneDrive for Business。 Microsoft はプライベート キーにアクセスできないので、暗号化されたデータは Microsoft に対して不透明なままです。 つまり、暗号化されたドキュメントを Web Apps でオンラインOffice表示できません。

## <a name="what-regions-and-languages-is-double-key-encryption-available-in-is-double-key-encryption-available-worldwide"></a>利用可能な二重キー暗号化とは、どの地域と言語ですか? ダブル キー暗号化は世界中で利用できますか?

DKE ラベルは、他の感度ラベルと同じ言語にローカライズMicrosoft Information Protection。 ダブル キー暗号化は世界中で利用できます。

## <a name="can-i-convert-a-non-dke-label-to-a-dke-label"></a>DKE 以外のラベルを DKE ラベルに変換できますか?

いいえ。 ラベルを作成した後は、DKE をラベルに追加できない。 代わりに、[ダブル キー暗号化を **使用する** ] を選択し、ラベルを作成するときに、ダブル キー暗号化サービスの URL を指定する必要があります。

## <a name="how-do-i-roll-my-dke-keys"></a>DKE キーをロールする方法

Azure に格納するキーのローリング (回転またはキー変更とも呼ばれる) の手順については [、「Operations for your Azure Information Protection テナント](/azure/information-protection/operations-customer-managed-tenant-key)キー」を参照してください。

DKE [サービスの新しいキーの](double-key-encryption.md#tenant-and-key-settings) 作成については、「テナントとキーの設定」を参照してください。

キーを作成するときに、名前と GUID を設定します。 次に、キーを回転する場合は、名前と GUID を持つ古いレコードを保持しますが、同じ名前で GUID が異なる新しいレコードを追加します。 新しいキーがアクティブとして設定され、公開キー API が新しい暗号化のために返しを開始します。 両方のキーを復号化して、新しいコンテンツと古いコンテンツを復号化できます。