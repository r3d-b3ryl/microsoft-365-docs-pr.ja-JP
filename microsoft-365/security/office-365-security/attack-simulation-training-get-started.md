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
description: 管理者は、攻撃シミュレーション トレーニングを使用して、Microsoft 365 E5 または Microsoft Defender でシミュレートされたフィッシング攻撃とパスワード攻撃を実行して、Office 365プラン 2 組織に対して実行する方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f6b8a10432c63a12f4d81e67f580f11b4f8b35ed
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2021
ms.locfileid: "60701205"
---
# <a name="get-started-using-attack-simulation-training-in-defender-for-office-365"></a>Defender での攻撃シミュレーション トレーニングの使用を開始Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Microsoft** Defender for [Office 365プラン 2 に適用されます](defender-for-office-365.md)

組織に Microsoft 365 E5 または Microsoft Defender for Office 365 Plan 2 (脅威[](office-365-ti.md)調査と対応機能を含む) がある場合は、Microsoft 365 Defender ポータルの攻撃シミュレーション トレーニングを使用して、組織で現実的な攻撃シナリオを実行できます。 これらのシミュレートされた攻撃は、実際の攻撃が一番下の行に影響を与える前に、脆弱なユーザーを特定して見つけるのに役立ちます。 詳細については、この記事を参照してください。

> [!NOTE]
> 攻撃シミュレーション トレーニングは、脅威管理攻撃シミュレーターのセキュリティ &コンプライアンス センターで使用された古い攻撃シミュレーター  v1 エクスペリエンスを \> **置き換** える。 <https://protection.office.com/attacksimulator>

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- Microsoft 365 Defender ポータルを開くには、<https://security.microsoft.com> にアクセスします。 攻撃シミュレーション のトレーニングは、メールと **コラボレーションの攻撃シミュレーション** \> **トレーニングで利用できます**。 攻撃シミュレーション のトレーニングに直接移動するには、を開きます <https://security.microsoft.com/attacksimulator> 。

- さまざまなサブスクリプション間で攻撃シミュレーション トレーニングを利用Microsoft 365詳細については[、「Microsoft Defender for Office 365」を参照してください](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)。

- この記事の手順を実行するには、Azure Active Directoryにアクセス許可を割り当てる必要があります。  具体的には、次のいずれかの役割のメンバーである必要があります。
  - **組織の管理**
  - **セキュリティ管理者**
  - **攻撃シミュレーション管理者** <sup>\*</sup> : 攻撃シミュレーション キャンペーンのすべての側面を作成および管理します。
  - **攻撃ペイロードの作成者** <sup>\*</sup> : 管理者が後で開始できる攻撃ペイロードを作成します。

  <sup>\*</sup>このロールにユーザーを追加すると、Microsoft 365 Defenderサポートされていません。

  詳細については、「管理者ポータル[のアクセス許可」または「Microsoft 365 Defenderロール](permissions-microsoft-365-security-center.md)[について」を参照してください](../../admin/add-users/about-admin-roles.md)。

- 攻撃シミュレーション トレーニングに対応する PowerShell コマンドレットはありません。

- 攻撃シミュレーションとトレーニング関連データは、他の顧客データと一緒に保存され、Microsoft 365されます。 詳細については、「データ[の場所Microsoft 365を参照してください](../../enterprise/o365-data-locations.md)。 攻撃シミュレーションは、NAM、APC、EUR、IND、CAN、AUS、FRA、GBR、JPN、KOR、BRA、LAM、CHE、NOR、ZAF、ARE、DEU の領域で使用できます。

  > [!NOTE]
  > NOR、ZAF、ARE、DEU が最新の追加です。 報告された電子メールテレメトリを除くすべての機能は、これらの地域で利用できます。 これを有効にし、報告された電子メールテレメトリが利用可能になったらすぐにお客様に通知します。 

- 2021 年 6 月 15 日現在、攻撃シミュレーション のトレーニングは、GCC。 組織に Office 365 G5 GCC または Microsoft Defender for Office 365 (プラン 2) がある場合は、Microsoft 365 Defender ポータルの攻撃シミュレーション トレーニングを使用して、この記事で説明したように、組織で現実的な攻撃シナリオを実行できます。 攻撃シミュレーションのトレーニングは、High 環境または DoD 環境GCCまだ利用できません。

> [!NOTE]
> 攻撃シミュレーショントレーニングは、E3 のお客様に試用版として機能のサブセットを提供します。 試用版には、Credential Harvest ペイロードを使用する機能と、'ISA フィッシング' または 'マス マーケット フィッシング' トレーニング エクスペリエンスを選択する機能が含まれています。 他の機能は、E3 試用版の一部です。

## <a name="simulations"></a>シミュレーション

*フィッシングは* 、正当な送信者または信頼できる送信者から見えるメッセージの機密情報を盗もうとする電子メール攻撃の一般的な用語です。 *フィッシングは* 、ソーシャル エンジニアリングとして分類される手法のサブセットの _一部です_。

攻撃シミュレーション トレーニングでは、次の複数の種類のソーシャル エンジニアリング手法を使用できます。

- **資格情報の取得**: 攻撃者は、URL を含むメッセージを受信者に送信します。 受信者が URL をクリックすると、通常、ユーザーにユーザー名とパスワードを求めるダイアログ ボックスが表示される Web サイトに移動します。 通常、ユーザーへの信頼を構築するために、宛先ページは既知の Web サイトを表すのが主な設定です。

- **マルウェアの添付** ファイル : 攻撃者は、添付ファイルを含むメッセージを受信者に送信します。 受信者が添付ファイルを開くと、任意のコード (マクロなど) がユーザーのデバイスで実行され、攻撃者が追加のコードをインストールしたり、自分自身をさらに定着させることが可能になります。

- **添付ファイルのリンク**: これは資格情報の収集のハイブリッドです。 攻撃者は、添付ファイル内の URL を含むメッセージを受信者に送信します。 受信者が添付ファイルを開き、URL をクリックすると、通常、ユーザーにユーザー名とパスワードを求めるダイアログ ボックスが表示される Web サイトに移動されます。 通常、ユーザーへの信頼を構築するために、宛先ページは既知の Web サイトを表すのが主な設定です。

- **マルウェアへのリンク**: 攻撃者は、既知のファイル共有サイト (たとえば、SharePoint Online または Dropbox) の添付ファイルへのリンクを含むメッセージを受信者に送信します。 受信者が URL をクリックすると、添付ファイルが開き、任意のコード (マクロなど) がユーザーのデバイス上で実行され、攻撃者が追加のコードをインストールしたり、自分自身をさらに定着させることが可能になります。

- **ドライブバイ URL**: 攻撃者は、URL を含むメッセージを受信者に送信します。 受信者が URL をクリックすると、バックグラウンド コードを実行しようとする Web サイトにアクセスされます。 このバックグラウンド コードは、受信者に関する情報を収集したり、デバイスに任意のコードを展開したりします。 通常、リンク先の Web サイトは、侵害された既知の Web サイトまたは既知の Web サイトの複製です。 Web サイトに関する理解は、リンクが安全にクリックできるとユーザーに理解を深めさせるのに役立ちます。 この手法は、ウォーターホール攻撃 _とも呼ばれる。_

> [!NOTE]
> フィッシング キャンペーンで URL を使用する前に、サポートされている Web ブラウザーでシミュレートされたフィッシング URL の可用性を確認してください。 多くの URL レピュテーション ベンダーと一緒に、これらのシミュレーション URL を常に許可しますが、必ずしも完全な範囲 (Google セーフ ブラウズなど) を持つとは限らない。 ほとんどのベンダーは、特定の URL (たとえば) を常に許可できるガイダンスを提供します <https://support.google.com/chrome/a/answer/7532419> 。

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

### <a name="create-a-simulation"></a>シミュレーションの作成

新しいシミュレーションを作成して送信する方法の手順については、「フィッシング攻撃をシミュレートする [」を参照してください](attack-simulation-training.md)。

### <a name="create-a-payload"></a>ペイロードの作成

シミュレーション内で使用するペイロードを作成する方法の手順については、「Create a custom payload for Attack Simulation [training」を参照してください](attack-simulation-training-payloads.md)。

### <a name="gaining-insights"></a>分析情報の取得

レポートで分析情報を得る方法の手順については、「攻撃シミュレーション トレーニングを通じてインサイトを得る [」を参照してください](attack-simulation-training-insights.md)。

> [!NOTE]
> 攻撃シミュレーターでは、Office 365 用 Defender の セーフ リンクを使用して、フィッシング キャンペーンのターゲット受信者に送信されるペイロード メッセージ内の URL のクリック データを安全に追跡します。セーフ Links ポリシーの [ユーザークリックを追跡しない] 設定がオンになっている場合でもです。
