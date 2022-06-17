---
title: Microsoft Defender for Business Premium 試用版プレイブック
f1.keywords:
- NOCSH
ms.author: v-kcirillo
author: cirilk
manager: dansimp
audience: Admin
ms.topic: conceptual
ms.collection: m365-security-compliance
ms.localizationpriority: high
ms.prod: m365-security
search.appverid:
- MOE150
- MET150
description: Microsoft 365 Business Premium 試用版を最大限に活用しましょう。 生産性とセキュリティに関する主要な機能を試してみてください。
ms.openlocfilehash: 740d0b394148a84434c13fd4a3fcd38e8c617c03
ms.sourcegitcommit: 66228a5506fdceb4cbf0d55b9de3f2943740134f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/15/2022
ms.locfileid: "66089778"
---
# <a name="trial-playbook-microsoft-business-premium"></a>試用版プレイブック: Microsoft Business Premium

Microsoft Business Premium 試用版プレイブックへようこそ。 このプレイブックは、Microsoft 365 Business Premium が生産性を向上させ、Defender for Business を使用して組織を保護する方法を教えることで、30 日間の無料試用版を最大限に活用するのに役立ちます。 Microsoft 推奨事項を使用して、Defender がどのように保護ポリシーの定義、組織への脅威の分析、サイバー攻撃への対応を可能にするかを学びます。

## <a name="set-up-the-microsoft-365-business-premium-trial"></a>Microsoft 365 Business Premium 試用版の設定

[Microsoft 365 Business Premium 試用版を開始するか、購入する](get-microsoft-365-business-premium.md) 場合、最初の手順は、すべてをセットアップすることです。

> [!Tip]
> プレイブック内のリンクがこの場所から移動したら、このプレイブックに戻って続行します。

まず、[試用期間を設定](../business-premium/m365bp-setup.md) します。

お客様が試用版の使用を開始し、セットアップ プロセスを完了した後、変更が有効になるまでに最大 2 時間かかる場合があります。

お使いの環境に[事前設定されたセキュリティ ポリシー](/security/office-365-security/preset-security-policies.md)を自動的に構成しました。 これらのポリシーは、ほとんどのユーザーに適したベースライン保護プロファイルを表します。 標準的な保護は以下のとおりです。

- 安全なリンク、安全な添付ファイル、フィッシング対策の各ポリシーは、テナント全体、または試用版のセットアップ プロセス時に選択したユーザーのサブセットに適用されます。

- SharePoint、OneDrive、Office アプリ、Microsoft Teams など、Microsoft 365 Business Premium のすべての機能に対する保護。

## <a name="add-a-domain"></a>ドメインの追加

Microsoft 365 Business Premium のトライアルを購入する際、所有するドメインを使用するか、サインアップ時にドメインを購入するかを選択することができます。

> [!Note]
> サインアップ時に新しいドメインを購入した場合、お客様のドメインはすべてセットアップされており、[ユーザーを追加してライセンスを割り当てる] に移動することができます。 管理センターにアクセスします ([https://admin.microsoft.com](https://admin.microsoft.com))。

1. 管理センターのメニューから **［セットアップ］** を選択してウィザードを開始します。

2. **［カスタム ドメインでメールをセットアップ］** を選択し、contoso.com などの **［既に所有しているドメインを使用］** します。

3. ウィザードの残りの手順に従って、プロセスを完了します。

   > [!Important]
   > サインアップ時にドメインを購入した場合、ここではドメインの追加ステップは表示されません。 代わりに [ユーザーの追加] に移動します。

4. ウィザードの手順に従って任意の DNS ホスティング プロバイダーで Office 365 用の DNS レコードを作成し、ドメインの所有を確認します。 ドメイン ホストがわかっている場合は、「Microsoft 365 にドメインを追加する」 を参照してください。

5. ご利用のホスティング プロバイダーが GoDaddy または Domain Connect を有効にした別のホストである場合、プロセスは簡単です。サインインし、お客様に代わって Microsoft が認証するよう自動的に求められます。

## <a name="onboard-and-protect-devices"></a>デバイスのオンボードと保護

1. Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) に移動してサインインします。

2. [セットアップ ウィザード](../security/defender-business/mdb-use-wizard.md) を実行する

3. [デバイスのオンボード](../security/defender-business/mdb-onboard-devices.md)。

4. [セキュリティ ポリシーをレビューする](../security/defender-business/mdb-configure-security-settings.md)。

## <a name="use-office-apps-on-devices"></a>デバイスで Office アプリを使用する

1. 最初に、[Office をインストール](m365bp-install-office-apps.md) する必要があります。

2. Office.com にアクセスして [サインイン](https://support.microsoft.com/office/get-started-at-office-com-91a4ec74-67fe-4a84-a268-f6bdf3da1804) します。

3. [Word ドキュメント](https://support.microsoft.com/office/basic-tasks-in-word-87b3243c-b0bf-4a29-82aa-09a681999fdc) などの Office ドキュメントを作成します。

4. チーム メンバーと [ドキュメントを共有](https://support.microsoft.com/office/share-your-documents-651e1cb9-9a51-46dc-8d32-bdb7d928eedd) します。

## <a name="start-using-the-microsoft-365-defender-portal"></a>Microsoft 365 Defender ポータルの使用を開始する 

1. [https://security.microsoft.com](https://security.microsoft.com) から Microsoft 365 Defender ポータルにアクセスします。

2. [ポータルを良く理解する](../security/defender-business/mdb-get-started.md) ため、時間を取って下さい。

3. そして、[セキュリティ体制にアクセス](../security/defender/microsoft-secure-score.md) します。

4. [セキュリティインシデントへの対応方法](../security/defender-business/mdb-respond-mitigate-threats.md) を良く理解するようにします。

5. 最後に、[修復処理について復習](../security/defender-business/mdb-review-remediation-actions.md) します。

## <a name="see-also"></a>関連項目

- [Microsoft 365 Business Premium &mdash; 中小企業向けサイバーセキュリティ](index.md)