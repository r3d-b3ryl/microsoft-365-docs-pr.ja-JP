---
title: 攻撃シミュレーション トレーニングの使用を開始する
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.custom:
- seo-marvel-apr2020
description: 管理者は、攻撃シミュレーション トレーニングを使用して、Microsoft 365 E5または計画 2 組織でシミュレートされたフィッシング攻撃とパスワード攻撃を実行Microsoft Defender for Office 365方法を学習できます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 244d0ae912a5cc2dc163b62f44b44877c0318b88
ms.sourcegitcommit: bcbcbd4ddc72ad2fed629619d23fac5827d072bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/29/2022
ms.locfileid: "64507413"
---
# <a name="get-started-using-attack-simulation-training-in-defender-for-office-365"></a>Defender for Office 365で攻撃シミュレーション トレーニングを使用する概要

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

[Microsoft Defender for Office 365プラン 2](defender-for-office-365.md) **に適用されます**

組織に[脅威の調査と対応機能](office-365-ti.md)を含む計画 2 Microsoft 365 E5またはMicrosoft Defender for Office 365がある場合は、Microsoft 365 Defender ポータルで攻撃シミュレーション トレーニングを使用して、組織で現実的な攻撃シナリオを実行できます。 これらのシミュレートされた攻撃は、実際の攻撃が収益に影響を与える前に、脆弱なユーザーを特定して見つけるのに役立ちます。 詳細については、この記事を参照してください。

> [!NOTE]
> 攻撃シミュレーション トレーニングは、Security & Compliance Center at **Threat Management** \> **Attack シミュレーター** または <https://protection.office.com/attacksimulator>.

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- Microsoft 365 Defender ポータルを開くには、<https://security.microsoft.com> にアクセスします。 攻撃シミュレーション トレーニングは、 **電子メールとコラボレーション** \> **の攻撃シミュレーション トレーニング** で利用できます。 攻撃シミュレーション トレーニングに直接移動するには、 <https://security.microsoft.com/attacksimulator>.

- さまざまなMicrosoft 365 サブスクリプション間での攻撃シミュレーション トレーニングの可用性の詳細については、[サービスの説明Microsoft Defender for Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)参照してください。

- この記事の手順を実行するには **、Azure Active Directory** でアクセス許可を割り当てる必要があります。 具体的には、次のいずれかのロールのメンバーである必要があります。
  - **グローバル管理者**
  - **セキュリティ管理者**
  - **攻撃シミュレーション管理者**<sup>\*</sup>: 攻撃シミュレーション キャンペーンのすべての側面を作成して管理します。
  - **攻撃ペイロード作成者**<sup>\*</sup>: 管理者が後で開始できる攻撃ペイロードを作成します。

  <sup>\*</sup>Microsoft 365 Defender ポータルでこのロールにユーザーを追加することは現在サポートされていません。

  詳細については、[Microsoft 365 Defender ポータルのアクセス許可](permissions-microsoft-365-security-center.md)または[管理者ロールについてを](../../admin/add-users/about-admin-roles.md)参照してください。

- 攻撃シミュレーション トレーニングに対応する PowerShell コマンドレットはありません。

- 攻撃シミュレーションとトレーニング関連データは、Microsoft 365 サービスの他の顧客データと共に格納されます。 詳細については、「[Microsoft 365データの場所](../../enterprise/o365-data-locations.md)」を参照してください。 攻撃シミュレーションは、NAM、APC、EUR、IND、CAN、AUS、FRA、GBR、JPN、KOR、BRA、LAM、CHE、NOR、ZAF、ARE、DEU の各リージョンで使用できます。

  > [!NOTE]
  > NOR、ZAF、ARE、DEU は最新の追加です。 報告された電子メール テレメトリを除くすべての機能は、これらのリージョンで使用できます。 これを有効にするよう取り組んでおり、報告された電子メール テレメトリが使用可能になるとすぐにお客様に通知します。

- 2021 年 6 月 15 日の時点で、攻撃シミュレーション トレーニングはGCCで利用できます。 組織に政府機関向けの G5 GCCまたはMicrosoft Defender for Office 365 (プラン 2) がOffice 365されている場合は、Microsoft 365 Defender ポータルで攻撃シミュレーション トレーニングを使用して、この記事で説明されているように、組織で現実的な攻撃シナリオを実行できます。 攻撃シミュレーション トレーニングは、GCC High または DoD 環境ではまだ使用できません。

> [!NOTE]
> 攻撃シミュレーション トレーニングは、試用版として E3 のお客様に機能のサブセットを提供します。 試用版には、Credential Harvest ペイロードを使用する機能と、"ISA フィッシング" または "Mass Market フィッシング" トレーニング エクスペリエンスを選択する機能が含まれています。 E3 試用版の一部には他の機能はありません。

## <a name="simulations"></a>シミュレーション

*フィッシング* とは、正当な送信者または信頼された送信者から見えるメッセージ内の機密情報を盗もうとする電子メール攻撃の一般的な用語です。 *フィッシング* は、 _ソーシャル エンジニアリング_ として分類する手法のサブセットの一部です。

攻撃シミュレーション トレーニングでは、さまざまな種類のソーシャル エンジニアリング手法を使用できます。

- **資格情報の収集**: 攻撃者は、URL を含むメッセージを受信者に送信します。 受信者が URL をクリックすると、通常、ユーザーにユーザー名とパスワードを尋ねるダイアログ ボックスが表示される Web サイトに移動します。 通常、宛先ページは、ユーザーの信頼を築くために、よく知られた Web サイトを表すようにテーマが設定されます。

- **マルウェアの添付ファイル**: 攻撃者は、添付ファイルを含むメッセージを受信者に送信します。 受信者が添付ファイルを開くと、任意のコード (マクロなど) がユーザーのデバイスで実行され、攻撃者が追加のコードをインストールしたり、さらに自分自身を固定したりするのに役立ちます。

- **添付ファイル内のリンク**: これは、資格情報の収集のハイブリッドです。 攻撃者は、添付ファイル内の URL を含むメッセージを受信者に送信します。 受信者が添付ファイルを開いて URL をクリックすると、通常、ユーザーにユーザー名とパスワードを尋ねるダイアログ ボックスが表示される Web サイトに移動します。 通常、宛先ページは、ユーザーの信頼を築くために、よく知られた Web サイトを表すようにテーマが設定されます。

- **マルウェアへのリンク**: 攻撃者は、既知のファイル共有サイト上の添付ファイルへのリンクを含むメッセージを受信者に送信します (SharePoint Online やDropboxなど)。 受信者が URL をクリックすると、添付ファイルが開き、ユーザーのデバイスで任意のコード (マクロなど) が実行され、攻撃者が追加のコードをインストールしたり、さらに自分自身を定着させたりするのに役立ちます。

- **Drive-by-url**: 攻撃者は、URL を含むメッセージを受信者に送信します。 受信者が URL をクリックすると、バックグラウンド コードを実行しようとする Web サイトに移動します。 このバックグラウンド コードは、受信者に関する情報を収集するか、デバイスに任意のコードをデプロイしようとします。 通常、宛先 Web サイトは、侵害された既知の Web サイト、または既知の Web サイトの複製です。 Web サイトに関する知識は、リンクをクリックしても安全であることをユーザーに伝えるのに役立ちます。 この手法は、 _水の穴攻撃_ とも呼ばれます。

> [!NOTE]
> フィッシング キャンペーンで URL を使用する前に、サポートされている Web ブラウザーでシミュレートされたフィッシング URL の可用性を確認してください。 多くの URL 評価ベンダーと協力してこれらのシミュレーション URL を常に許可していますが、常に完全なカバレッジを持つわけではありません (Google セーフ参照など)。 ほとんどのベンダーは、特定の URL (たとえば) <https://support.google.com/chrome/a/answer/7532419>を常に許可できるガイダンスを提供しています。

攻撃シミュレーション トレーニングで使用される URL については、次の一覧で説明します。

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

新しいシミュレーションを作成して送信する方法の詳細な手順については、「 [フィッシング攻撃をシミュレートする](attack-simulation-training.md)」を参照してください。

### <a name="create-a-payload"></a>ペイロードを作成する

シミュレーション内で使用するペイロードを作成する方法の詳細な手順については、「 [攻撃シミュレーション トレーニング用のカスタム ペイロードを作成する](attack-simulation-training-payloads.md)」を参照してください。

### <a name="gaining-insights"></a>分析情報を取得する

レポートを使用して分析情報を取得する方法の詳細な手順については、「 [攻撃シミュレーション トレーニングを通じて分析情報を取得する](attack-simulation-training-insights.md)」を参照してください。

> [!NOTE]
> 攻撃シミュレーターでは、Defender for Office 365の セーフ リンクを使用して、フィッシング キャンペーンの対象となる受信者に送信されるペイロード メッセージ内の URL のクリック データを安全に追跡します(セーフ リンク ポリシーの [ユーザーのクリックの **追跡**] 設定がオフになっている場合でも)。
