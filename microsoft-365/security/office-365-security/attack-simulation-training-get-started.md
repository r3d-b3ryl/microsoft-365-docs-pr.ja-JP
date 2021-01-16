---
title: 攻撃シミュレーション トレーニングの使用を開始する
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: da5845db-c578-4a41-b2cb-5a09689a551b
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.custom:
- seo-marvel-apr2020
description: 管理者は、Microsoft 365 E5 または microsoft Defender for Office 365 プラン 2 の組織で、攻撃シミュレーション トレーニングを使用してシミュレートされたフィッシングとパスワード攻撃を実行する方法について説明します。
ms.openlocfilehash: 2c00fb27748887c6b8e2fa1458b10f0c3405eef7
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/15/2021
ms.locfileid: "49877166"
---
# <a name="get-started-using-attack-simulation-training"></a>攻撃シミュレーション トレーニングの使用を開始する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

組織に Microsoft 365 E5 または microsoft Defender for Office 365[](office-365-ti.md)プラン 2 (脅威の調査と対応の機能を含む) がある場合は、Microsoft セキュリティ センターの攻撃シミュレーション トレーニングを使用して、組織で現実的な攻撃シナリオを実行できます。 これらのシミュレートされた攻撃は、実際の攻撃が下線に影響を与える前に、脆弱なユーザーを特定して見つけるのに役立ちます。 詳細については、この記事を参照してください。

> [!NOTE]
> 攻撃シミュレーション トレーニングは、Microsoft Defender for Office [365](attack-simulator.md)の攻撃シミュレーターで説明されている、古い攻撃シミュレーター v1 エクスペリエンスに取って代わるものになります。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- Microsoft セキュリティ センターを開くには、次のアクセス先に移動します <https://security.microsoft.com/> 。 攻撃シミュレーション トレーニングは、電子メールとコラボレーション **の攻撃シミュレーション** \> **トレーニングで利用できます**。 直接攻撃シミュレーション トレーニングに移動するには、開きます <https://security.microsoft.com/attacksimulator> 。

- さまざまな Microsoft 365 サブスクリプションで攻撃シミュレーション トレーニングを利用する方法について詳しくは、Microsoft Defender で Office [365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)サービスの説明をご覧ください。

- この記事の手順を実行する前に、セキュリティ & コンプライアンス センターまたは Azure Active Directory でアクセス許可を割り当てる必要があります。 具体的には、組織の管理、セキュリティ管理者、または次のいずれかの役割のメンバーである必要があります。
  - **攻撃シミュレータ管理者**: 攻撃シミュレーション キャンペーンのすべての側面を作成および管理します。
  - **攻撃シミュレータペイロード作成者**: 管理者が後で開始できる攻撃ペイロードを作成します。

  詳細については、「セキュリティ/コンプライアンス センター [の](permissions-in-the-security-and-compliance-center.md) アクセス許可」または「& [について」を参照してください](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)。

- 攻撃シミュレーション トレーニング用の対応する PowerShell コマンドレットはありません。

- 攻撃シミュレーションとトレーニング関連データは、Microsoft 365 サービスの他の顧客データと一緒に保存されます。 詳細については [、Microsoft 365 のデータの場所を参照してください](/microsoft-365/enterprise/o365-data-locations)。 攻撃シミュレーションは現在、SGP、NOR、UAE、ZAF、GER、BRA、CHE の地域では利用できません。

## <a name="simulations"></a>シミュレーション

*フィッシングは* 、正当な送信者または信頼できる送信者から見えるメッセージ内の機密情報を盗もうとする電子メール攻撃の一般的な用語です。 *フィッシングは* 、ソーシャル エンジニアリングとして分類する手法のサブセットの _一部です_。

攻撃シミュレーション トレーニングでは、次の複数の種類のソーシャル エンジニアリング手法を利用できます。

- **資格情報の取得**: 攻撃者は、URL を含むメッセージを受信者に送信します。 受信者が URL をクリックすると、通常はユーザー名とパスワードを求めるダイアログ ボックスが表示される Web サイトに移動します。 通常、宛先ページは、ユーザーの信頼を構築するために、既知の Web サイトを表すメッセージです。

- **マルウェアの添付** ファイル : 攻撃者が、添付ファイルを含むメッセージを受信者に送信します。 受信者が添付ファイルを開くと、ユーザーのデバイスで任意のコード (マクロなど) が実行され、攻撃者が追加のコードをインストールしたり、それ自体をさらに進めることができます。

- **添付ファイル内のリンク**: これは資格情報取得のハイブリッドです。 攻撃者は、添付ファイル内の URL を含むメッセージを受信者に送信します。 受信者が添付ファイルを開いて URL をクリックすると、通常はユーザー名とパスワードを求めるダイアログ ボックスが表示される Web サイトに移動します。 通常、宛先ページは、ユーザーの信頼を構築するために、既知の Web サイトを表すメッセージです。

- **マルウェアへのリンク**: 攻撃者は、既知のファイル共有サイト (SharePoint Online や Dropbox など) 上の添付ファイルへのリンクを含むメッセージを受信者に送信します。 受信者が URL をクリックすると、添付ファイルが開き、ユーザーのデバイス上で任意のコード (マクロなど) が実行され、攻撃者が追加のコードをインストールしたり、自分自身をさらに進めることができます。

- **ドライブバイ URL**: 攻撃者が、URL を含むメッセージを受信者に送信します。 受信者が URL をクリックすると、バックグラウンド コードの実行を試みる Web サイトにリダイレクトされます。 このバックグラウンド コードは、受信者に関する情報を収集するか、デバイスに任意のコードを展開します。 通常、リンク先の Web サイトは、侵害された既知の Web サイト、または既知の Web サイトの複製です。 Web サイトに精通すると、リンクが安全にクリックできるとユーザーを説得できます。 この手法は、水の穴攻撃 _とも呼ばれる手法です_。

> [!NOTE]
> フィッシング キャンペーンで URL を使用する前に、サポートされている Web ブラウザーでシミュレートされたフィッシング URL の可用性を確認します。 多くの URL 評価ベンダーと一緒に、これらのシミュレーション URL を常に許可しますが、必ずしも完全に対応できるとは限らない (Google セーフ ブラウズなど)。 ほとんどのベンダーは、特定の URL (たとえば) を常に許可できるガイダンスを提供します <https://support.google.com/chrome/a/answer/7532419> 。

攻撃シミュレーション トレーニングで使用される URL を次の一覧に示します。

- <https://www.mcsharepoint.com>
- <https://www.attemplate.com>
- <https://www.doctricant.com>
- <https://www.mesharepoint.com>
- <https://www.officence.com>
- <https://www.officenced.com>
- <https://www.officences.com>
- <https://www.officentry.com>
- <https://www.officested.com>
- <https://www.prizegives.com>
- <https://www.prizemons.com>
- <https://www.prizewel.com>
- <https://www.prizewings.com>
- <https://www.shareholds.com>
- <https://www.sharepointen.com>
- <https://www.sharepointin.com>
- <https://www.sharepointle.com>
- <https://www.sharesbyte.com>
- <https://www.sharession.com>
- <https://www.sharestion.com>
- <https://www.templateau.com>
- <https://www.templatent.com>
- <https://www.templatern.com>
- <https://www.windocyte.com>

### <a name="create-a-simulation"></a>シミュレーションを作成する

新しいシミュレーションを作成して送信する方法の詳しい手順については、「フィッシング攻撃をシミュレートする [」を参照してください](attack-simulation-training.md)。

### <a name="create-a-payload"></a>ペイロードを作成する

シミュレーション内で使用するペイロードを作成する手順については、「攻撃シミュレーション トレーニング用のカスタム ペイロードを作成する」を [参照してください](attack-simulation-training-payloads.md)。

### <a name="gaining-insights"></a>分析情報の取得

レポートを使用して分析情報を得る方法の詳しい手順については、「攻撃シミュレーション トレーニングによる分析情報の取得」 [をご覧ください](attack-simulation-training-insights.md)。
