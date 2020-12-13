---
title: 二重キー暗号化の概要と FAQ
description: Microsoft 365 の二重キー暗号化についてよく寄せられる質問です。
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
ms.openlocfilehash: 32686e76018d8b6a361ea99e6b00271b9547ed95
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663062"
---
# <a name="double-key-encryption-frequently-asked-questions"></a>二重キー暗号化についてよく寄せられる質問

二重キー暗号化のしくみについて質問がありますか? ここで回答を確認してください。

## <a name="what-is-double-key-encryption-for-microsoft-365-dke"></a>Microsoft 365 (DKE) の二重キー暗号化とは

Microsoft 365 の二重キー暗号化を使用すると、機密性の高いデータを保護して、特殊な要件を満たします。 これにより、お客様は暗号化キーの完全な制御を維持できます。 データを保護するために 2 つのキーを使用します。コントロール内の 1 つのキーと、Microsoft Azure に安全に保存された 2 番目のキー。 二重キー暗号化で保護されたデータを表示するには、両方のキーにアクセスする必要があります。 Microsoft はこれらのキーの 1 つしかアクセスできないので、保護されたデータに Microsoft はアクセスできなくなり、データのプライバシーとセキュリティを完全に制御できます。  

選択した場所 (オンプレミスのキー管理サーバーまたはクラウド内) で、キーの要求に使用する二重キー暗号化サービスをホストできます。 他のアプリケーションと同じ方法でサービスを維持します。 二重キー暗号化を使用すると、Double Key Encryption サービスへのアクセスを制御できます。 機密性の高いデータをオンプレミスで保存したり、クラウドに移動することができます。 キーのフル コントロールを維持するために、サード パーティ製のアクセスを防止できます。 二重キー暗号化を使用すると、データとキーを同じ場所に格納できます。

DKE は、一般データ保護規則 (GDPR)、医療保険の移植性と責任に関する法律 (HIPAA)、グレーム リーチ ブライリー法 (GLBA)、ロシアのデータローカリゼーション法 (連邦法 No) など、いくつかの規制および基準に関する規制要件を満たすのに役立ちます。 242-NZ、オーストラリアの連邦プライバシー法 1988 年、ニュージーランドのプライバシー法 1993

## <a name="can-i-use-double-key-encryption-with-microsoft-office-built-in-sensitivity-labeling"></a>二重キー暗号化を組み込みのMicrosoft Officeラベル付けで使用できますか。

二重キー暗号化を使用してドキュメントを保護するには、Azure Information Protection 統合ラベル付けクライアントを使用する必要があります。 現時点では、組み込みのMicrosoft Officeラベルを使用することはできません。

## <a name="what-microsoft-365-apps-can-i-use-with-dke"></a>DKE で使用できる Microsoft 365 アプリ

DKE ラベルを使用すると、Windows 上の Word、Excel、PowerPoint のデスクトップ バージョンを使用してドキュメントを保護できます。 Windows で *.12711 以降 (Word、PowerPoint、Excel のデスクトップ バージョン) を使用している必要があります。

## <a name="how-is-double-key-encryption-different-from-the-existing-hold-your-own-key-hyok-solution"></a>Double Key Encryption と既存の保持独自のキー (HYOK) ソリューションの違いは何ですか?

二重キー暗号化は、2 つのキーでデータを暗号化します。 暗号化キーが制御され、2 番目のキーが Microsoft Azure に保存され、暗号化されたデータをクラウドに移動できます。 HYOK は 1 つのキーだけでコンテンツを保護し、キーは常にオンプレミスです。  

## <a name="can-double-key-encrypted-documents-be-shared-externally"></a>二重キー暗号化ドキュメントを外部で共有できますか。

二重キー暗号化ドキュメントは、次のユーザーに限り、別のテナントのユーザーと共有できます。

- Double Key Encryption サービスでキーにアクセスするために必要なアクセス許可を持っている。

- Microsoft Azure でキーにアクセスするために必要なアクセス許可を持っている。

## <a name="what-happens-to-documents-that-are-protected-with-hyok"></a>HYOK で保護されているドキュメントは何が起こりますか?

二重キー暗号化を展開しても、既存の HYOK セットアップには影響しません。 ただし、HYOK と並行して二重キー暗号化の使用を開始することをお勧めします。

## <a name="can-i-run-double-key-encryption-in-my-non-microsoft-air-gapped-environment"></a>Microsoft 以外のエアガップ環境で二重キー暗号化を実行できますか。

サービスには Microsoft Azure へのアクセスが必要なので、DKE はこれらの環境をサポートしません。

## <a name="where-can-i-store-double-key-encrypted-documents"></a>二重キー暗号化ドキュメントはどこで保存できますか。

二重キー暗号化ドキュメントは、オンプレミスまたはクラウドに保存できます。 クラウドでは、暗号化されたコンテンツを SharePoint Online と OneDrive for Business に移動できます。 Microsoft はユーザーのプライベート キーにアクセスできないので、暗号化されたデータは Microsoft に対して不透明なままです。 これは、暗号化されたドキュメントを Web Apps でオンラインでOfficeも意味します。

## <a name="what-regions-and-languages-is-double-key-encryption-available-in-is-double-key-encryption-available-worldwide"></a>二重キー暗号化を使用できる地域と言語は何ですか? 二重キー暗号化は世界中で利用できますか?

DKE ラベルは、Microsoft Information Protection の他の区別ラベルと同じ言語にローカライズされます。 二重キー暗号化は世界中で利用できます。

## <a name="can-i-convert-a-non-dke-label-to-a-dke-label"></a>DKE 以外のラベルを DKE ラベルに変換できますか。

いいえ。 DKE を作成した後でラベルに追加できない。 代わりに、[二重キー暗号化を使用する] を選択し、ラベルの作成時に Double Key Encryption サービスの URL を指定する必要があります。

## <a name="how-do-i-roll-my-dke-keys"></a>DKE キーをロールする方法

Azure に格納するキーのローリング (回転または再キー処理とも呼ばれる) の手順については [、「Azure Information Protection](https://docs.microsoft.com/azure/information-protection/operations-customer-managed-tenant-key)テナント キーの操作」を参照してください。

DKE [サービスの新しいキーの](double-key-encryption.md#tenant-and-key-settings) 作成については、「テナントとキーの設定」を参照してください。

キーを作成するときに、名前と GUID を設定します。 キーを回転させる場合は、名前と GUID を持つ古いレコードを保持しますが、同じ名前で GUID が異なる新しいレコードを追加します。 新しいキーがアクティブとして設定され、公開キー API が新しい暗号化のためにキーを返し始める。 新しいコンテンツと古いコンテンツを解読できるよう、両方のキーを復号化に使用できます。
