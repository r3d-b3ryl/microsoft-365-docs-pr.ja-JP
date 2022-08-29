---
title: Microsoft Defender for Business Premium 試用版プレイブック
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: Admin
ms.topic: conceptual
ms.collection: m365-security-compliance
ms.localizationpriority: high
ms.date: 08/24/2022
ms.prod: m365-security
search.appverid:
- MOE150
- MET150
description: Microsoft 365 Business Premium 試用版を最大限に活用しましょう。 生産性とセキュリティに関する主要な機能を試してみてください。
ms.openlocfilehash: 750772357c5dda926840ba41f879a055e12d5230
ms.sourcegitcommit: 2d1302a6165b83cbbc8c2df2c608d43b6b0498b0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2022
ms.locfileid: "67433446"
---
# <a name="trial-playbook-microsoft-business-premium"></a>試用版プレイブック: Microsoft Business Premium

Microsoft Business Premium 試用版プレイブックへようこそ。 このプレイブックは、Microsoft 365 Business Premium が生産性を向上させ、高度なセキュリティ機能で組織を保護する方法を体験することで、30 日間の無料トライアルを最大限に活用するのに役立ちます。 Microsoft の推奨事項を使用して、脅威に対する保護機能を設定し、検出された脅威を分析し、サイバー攻撃に対応する方法について説明します。

## <a name="set-up-the-microsoft-365-business-premium-trial"></a>Microsoft 365 Business Premium 試用版の設定

[Microsoft 365 Business Premium 試用版を開始するか、購入する](get-microsoft-365-business-premium.md) 場合、最初の手順は、すべてをセットアップすることです。

> [!TIP]
> このプレイブックをブラウザーのお気に入りに保存します。 プレイブック内のリンクがこの場所から移動したら、このプレイブックに戻って続行します。

まず、[試用期間を設定](../business-premium/m365bp-setup.md) します。

試用版を開始してセットアップ プロセスを完了すると、変更が有効になるまで最大で 2 時間かかる場合があります。

Microsoft 365 Business Premium には、環境で使用できる[事前設定済みセキュリティ ポリシー](/security/office-365-security/preset-security-policies.md)が含まれています。 これらのポリシーは、ほとんどのユーザーに適したベースライン保護プロファイルを表します。 標準的な保護は以下のとおりです。

- [安全なリンク](../security/office-365-security/safe-links.md)、[安全な添付ファイル](../security/office-365-security/safe-attachments.md)、[フィッシング対策](../security/office-365-security/anti-phishing-protection.md)の各ポリシーは、テナント全体、または試用版のセットアップ プロセス時に選択したユーザーのサブセットに適用されます。 (試用版のサブスクリプションは最大 25 人のユーザーを対象とします)。

- [SharePoint](/sharepoint/introduction)、[OneDrive](/onedrive/one-drive-quickstart-small-business)、[Office アプリ](/deployoffice/about-microsoft-365-apps)、[Microsoft Teams](/microsoftteams/teams-overview) などの生産性アプリの保護。

## <a name="add-a-domain"></a>ドメインの追加

Microsoft 365 Business Premium 体験版取得または購入する際、自分の所有しているドメインを使用するか、サインアップ時にドメインを購入するかを選択することができます。

> [!NOTE]
> サインアップ時に新しいドメインを購入した場合、お客様のドメインはすべてセットアップされており、[ユーザーを追加してライセンスを割り当てる] に移動することができます。 管理センターにアクセスします ([https://admin.microsoft.com](https://admin.microsoft.com))。

1. 管理センターのメニューから **［セットアップ］** を選択してウィザードを開始します。

2. **［カスタム ドメインでメールをセットアップ］** を選択し、[**既に所有しているドメインを使用**] (`contoso.com` など) を選択します。

3. ウィザードの残りの手順に従って、プロセスを完了します。

   > [!Important]
   > サインアップ時にドメインを購入した場合、ここでは[**ドメインの追加**] 手順は表示されません。 代わりに [**ユーザーの追加**] に移動します。

4. ウィザードの手順に従って[任意の DNS ホスティング プロバイダーで Office 365 用の DNS レコードを作成](/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)し、ドメインを所持していることを確認します。 ドメイン ホストがわかっている場合は、「[Microsoft 365 にドメインを追加する](/microsoft-365/admin/setup/add-domain)」 を参照してください。

5. ホスティング プロバイダーが GoDaddy またはドメイン接続が有効になっている別のホストである場合は、サインインし、Microsoft が自動的に認証するように求められます。

## <a name="onboard-and-protect-devices"></a>デバイスのオンボードと保護

Microsoft 365 Business Premiumには、デバイスを保護するための新しいセキュリティ ソリューションである Defender for Business が含まれています。 「[デバイスを Microsoft Defender for Business にオンボードするデバイスを Microsoft Defender for Business にオンボードする](../security/defender-business/mdb-onboard-devices.md)」を参照してください。

1. Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) に移動してサインインします。

2. [セットアップ ウィザード](../security/defender-business/mdb-use-wizard.md) を実行する

3. [デバイスのオンボード](../security/defender-business/mdb-onboard-devices.md)。

4. [セキュリティ ポリシーのレビュー](../security/defender-business/mdb-configure-security-settings.md)。

## <a name="use-microsoft-365-apps-on-devices"></a>デバイスでMicrosoft 365 Appsを使用する

1. まず、[Microsoft 365 Appsをインストール](m365bp-install-office-apps.md)する必要があります。

2. [https://office.com](https://office.com) に移動し、サインインします。 ([Office.com のはじめにを](https://support.microsoft.com/office/get-started-at-office-com-91a4ec74-67fe-4a84-a268-f6bdf3da1804)参照してください)。

3. [Word ドキュメント](https://support.microsoft.com/office/basic-tasks-in-word-87b3243c-b0bf-4a29-82aa-09a681999fdc) などの Office ドキュメントを作成します。

4. チーム メンバーと [ドキュメントを共有](https://support.microsoft.com/office/share-your-documents-651e1cb9-9a51-46dc-8d32-bdb7d928eedd) します。

## <a name="start-using-the-microsoft-365-defender-portal"></a>Microsoft 365 Defender ポータルの使用を開始する 

1. [https://security.microsoft.com](https://security.microsoft.com) から Microsoft 365 Defender ポータルにアクセスします。

2. [ポータルを良く理解する](../security/defender-business/mdb-get-started.md) ため、時間を取って下さい。

3. 次 [に、セキュリティ体制を評価](../security/defender/microsoft-secure-score.md)し、スコアを向上させる方法を確認します。

4. [セキュリティ インシデントに対応する](../security/defender-business/mdb-respond-mitigate-threats.md)方法について説明します。

5. 最後に、[修復処理について復習](../security/defender-business/mdb-review-remediation-actions.md) します。

## <a name="see-also"></a>関連項目

- [Microsoft 365 Business Premium - 小規模ビジネス向けのサイバーセキュリティ](index.md)
- [Defender for Business とは?](../security/defender-business/mdb-overview.md)