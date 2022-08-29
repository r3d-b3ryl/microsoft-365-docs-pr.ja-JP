---
title: ネットワーク保護を使用して、Linux が不正なサイトに接続するのを防ぐ
description: Linux ユーザーが既知の悪意のある不審なネットワーク アドレスにアクセスできないようにしてネットワークを保護する
keywords: ネットワーク保護、Linux エクスプロイト、悪意のある Web サイト、IP、ドメイン、ドメイン、コマンドと制御、SmartScreen、トースト通知
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
audience: ITPro
author: jweston-1
ms.author: v-jweston
ms.reviewer: oogunrinde
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.topic: overview
ms.collection:
- m365initiative-m365-defender
- M365-security-compliance
ms.date: ''
ms.openlocfilehash: 5a4fcb8e467a9ec79a03b27d8e8260406a615a54
ms.sourcegitcommit: d09eb780dc41a01796eb8137fbe9267231af6746
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2022
ms.locfileid: "67385951"
---
# <a name="network-protection-for-linux"></a>Linux のネットワーク保護

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**

- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!IMPORTANT]
> 一部の情報は、市販される前に大幅に変更される可能性があるプレリリース製品に関するものです。 Microsoft は、ここに記載された情報に関して、明示または黙示を問わず、いかなる保証も行いません。

## <a name="overview"></a>概要

Microsoft は、Network Protection 機能を Linux に導入しています。

ネットワーク保護は、インターネット ベースのイベントからデバイスの攻撃面を減らすのに役立ちます。 これにより、従業員がアプリケーションを使用して、ホストされる可能性のある危険なドメインにアクセスできなくなります。

- フィッシング詐欺
- 悪用
- インターネット上の他の悪意のあるコンテンツ

ネットワーク保護により、Microsoft Defender [SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview.md) の範囲が拡大され、低評価ソースへの接続を試みるすべての送信 HTTP トラフィックがブロックされます。 送信 HTTP トラフィックのブロックは、ドメインまたはホスト名に基づいています。

## <a name="web-content-filtering-for-linux"></a>Linux の Web コンテンツ フィルター

Linux 用ネットワーク保護を使用してテストするには、Web コンテンツ フィルターを使用できます。 [Web コンテンツ のフィルター処理に関するページを](web-content-filtering.md)参照してください。

### <a name="known-issues"></a>既知の問題

- Network Protection は、仮想プライベート ネットワーク (VPN) トンネルとして実装されます。 カスタム nftables/iptables スクリプトを使用した高度なパケット ルーティング オプションを使用できます。
- UX をブロック/警告できません
  - お客様からのフィードバックが収集され、設計の改善が進んでいます

> [!NOTE]
> Linux Web Threat Protection の有効性を評価するには、すべてのディストリビューションの既定値である Firefox ブラウザーを使用することをお勧めします。

### <a name="prerequisites"></a>前提条件

- ライセンス: Microsoft Defender for Endpoint テナント (試用可能) と、[Windows 以外](non-windows.md#licensing-requirements)のプラットフォームのMicrosoft Defender for Endpointで見つかったプラットフォーム固有の要件
- オンボードされたマシン:
  - **最小 Linux バージョン**: サポートされているディストリビューションの一覧については、「[Linux でのMicrosoft Defender for Endpoint」を](microsoft-defender-endpoint-linux.md)参照してください。
  - **Microsoft Defender for Endpoint Linux クライアント バージョン**: 101.78.13 -insiderSlow(Preview)

## <a name="instructions"></a>手順

Linux を手動でデプロイする方法については、「[Microsoft Defender for Endpoint on Linux を手動でデプロイする](linux-install-manually.md)」を参照してください。

次の例は、insiders-Slow チャネル用の ubuntu 20.04 の mdatp パッケージに必要な一連のコマンドを示しています。

```bash
curl -o microsoft.list https://packages.microsoft.com/config/ubuntu/20.04/insiders-slow.list 
sudo mv ./microsoft.list /etc/apt/sources.list.d/microsoft-insiders-slow.list 
sudo apt-get install gpg 
curl https://packages.microsoft.com/keys/microsoft.asc | sudo apt-key add - 
sudo apt-get install apt-transport-https 
sudo apt-get update 
sudo apt install -y mdatp 
```

### <a name="device-onboarding"></a>デバイスのオンボード

デバイスをオンボードするには、Linux サーバー用の Python オンボード パッケージを Microsoft 365 Defender -> Settings -> デバイス管理 -> Onboarding からダウンロードして実行する必要があります。

```bash
sudo python3 MicrosoftDefenderATPOnboardingLinuxServer.py 
```

### <a name="manually-enable-network-protection"></a>ネットワーク保護を手動で有効にする

1. "networkProtection" 機能をオンにし、"/etc/opt/microsoft/mdatp/wdacfg" を編集し、 **networkProtection** を **有効** に設定します。  
2. 次のコマンドを実行して、mdatp サービスを再起動します。

```bash
sudo systemctl restart mdatp 
```
> :::image type="content" source="images/network-protection-linux-mdatp-restart.png" alt-text="Linux mdatp の再起動を示します。" lightbox="images/network-protection-linux-mdatp-restart.png":::

### <a name="configure-the-enforcement-level"></a>適用レベルを構成する

ネットワーク保護は既定では無効になっていますが、次のいずれかのモード (強制レベルとも呼ばれます) で実行するように構成できます。

- **監査**: 基幹業務アプリに影響しないようにしたり、ブロックが発生する頻度を把握したりするのに役立ちます
- **ブロック**: ネットワーク保護により、悪意のある Web サイトへの接続が防止されます
- **無効**: Network Protection に関連付けられているすべてのコンポーネントが無効になっている

```bash
sudo mdatp config network-protection enforcement-level --value block
```

or

```bash
sudo mdatp config network-protection enforcement-level --value audit
```

Network Protection が正常に開始されたことを確認するには、ターミナルから次のコマンドを実行します。"started" が出力されることを確認します。

```bash
mdatp health --field network_protection_status
```

### <a name="validation"></a>Validation

A. ネットワーク保護が常にブロックされているサイトに影響を与えているかどうかを確認します。

- [http://www.smartscreentestratings2.net](http://www.smartscreentestratings2.net)
- [https://www.smartscreentestratings2.net](https://www.smartscreentestratings2.net)
- [http://malw-090-0-1.phsh-005-0-1.smartscreentestratings.com/](http://malw-090-0-1.phsh-005-0-1.smartscreentestratings.com/)

B. 診断ログを調べる

```bash
$ sudo mdatp log level set --level debug 
$ sudo tail -f /var/log/microsoft/mdatp/microsoft_defender_np_ext.log 
```

#### <a name="to-exit-the-validation-mode"></a>検証モードを終了するには

ネットワーク保護を無効にし、ネットワーク接続を再起動します。

```bash
$ sudo mdatp config network-protection enforcement-level --value disabled
```

## <a name="advanced-configuration"></a>高度な構成

既定では、Linux ネットワーク保護は既定のゲートウェイでアクティブです。ルーティングとトンネリングは内部的に構成されます。
ネットワーク インターフェイスをカスタマイズするには、**/opt/microsoft/mdatp/conf/** 構成ファイルから **networkSetupMode** パラメーターを変更し、サービスを再起動します。

```bash
sudo systemctl restart  mdatp 
```

また、構成ファイルを使用すると、ユーザーは次の項目をカスタマイズできます。

- プロキシ設定
- SSL 証明書ストア
- トンネリング デバイス名
- IP
- その他

[Linux 上のMicrosoft Defender for Endpoint](microsoft-defender-endpoint-linux.md)で説明されているように、すべてのディストリビューションの既定値がテストされました

### <a name="microsoft-defender-portal"></a>Microsoft Defender ポータル

また、 **Microsoft Defender** > **Settings** > **Endpoints** > **Advanced 機能** で **、"カスタム ネットワーク インジケーター"** トグルが _有効_ に設定されていることを確認します。

> [!IMPORTANT]
> 上記 **の "カスタム ネットワーク インジケーター"** トグルは、Windows を含む Network Protection サポートを備えたすべてのプラットフォームに対する **カスタム インジケーター** の有効化を制御します。 Windows では、インジケーターを適用するには、Network Protection も明示的に有効にする必要があります。

>:::image type="content" source="images/network-protection-linux-defender-security-center-advanced-features-settings.png" alt-text="MEM Create Profile" lightbox="images/network-protection-linux-defender-security-center-advanced-features-settings.png":::

## <a name="how-to-explore-the-features"></a>機能を調べる方法

1. Web 脅威保護を使用して [Web 脅威から組織を保護する](web-threat-protection.md) 方法について説明します。
   - Web 脅威保護は、Microsoft Defender for Endpointにおける Web 保護の一部です。 ネットワーク保護を使用して、Web の脅威からデバイスを保護します。
2. [カスタム インジケーターの種類のブロックを](indicator-ip-domain.md)取得するには、侵害のカスタム インジケーター フローを実行します。
3. [Web コンテンツ のフィルター処理について説明します](web-content-filtering.md)。
   > [!NOTE]
   > ポリシーを削除する場合、またはデバイス グループを同時に変更する場合は、ポリシーの展開が遅れる可能性があります。
   > プロのヒント: デバイス グループ上のカテゴリを選択せずにポリシーを展開できます。 このアクションは、ブロック ポリシーを作成する前にユーザーの動作を理解するのに役立つ監査のみのポリシーを作成します。
4. [Microsoft Defender for EndpointとCloud App Securityを統合](/defender-cloud-apps/mde-integration.md)すると、ネットワーク保護が有効な macOS デバイスにはエンドポイント ポリシー適用機能が備わります。
   > [!NOTE]
   > 検出とその他の機能は、現在、これらのプラットフォームではサポートされていません。

## <a name="scenarios"></a>シナリオ

パブリック プレビューでは、次のシナリオがサポートされます。

### <a name="web-threat-protection"></a>Web の脅威に対する保護

Web 脅威保護は、Microsoft Defender for Endpointにおける Web 保護の一部です。 ネットワーク保護を使用して、Web の脅威からデバイスを保護します。 Microsoft Edge や Chrome や Firefox などの一般的なサードパーティのブラウザーと統合することで、Web 脅威保護は Web プロキシなしで Web の脅威を停止します。 Web 脅威保護は、オンプレミスまたは離れた場所にいるデバイスを保護できます。 Web 脅威保護は、次の種類のサイトへのアクセスを停止します。

- フィッシング サイト
- マルウェア ベクター
- サイトを悪用する
- 信頼されていないサイトまたは低評価サイト
- カスタム インジケーターの一覧でブロックしたサイト

>:::image type="content" source="images/network-protection-reports-web-protection.png" alt-text="Web Protection は、Web 脅威の検出を報告します。" lightbox="images/network-protection-reports-web-protection.png":::

詳細については、「[Web 脅威から組織を保護する](web-threat-protection.md)」を参照してください。

#### <a name="custom-indicators-of-compromise"></a>侵害のカスタム インジケーター  

侵害インジケーター (IoCs) マッチングは、すべてのエンドポイント保護ソリューションで不可欠な機能です。 この機能により、SecOps は検出およびブロック (防止と応答) のインジケーターの一覧を設定できます。

エンティティの検出、防止、除外を定義するインジケーターを作成します。 実行するアクションと、アクションを適用する期間と、それを適用するデバイス グループのスコープを定義できます。

現在サポートされているソースは、Defender for Endpoint のクラウド検出エンジン、自動調査と修復エンジン、エンドポイント防止エンジン (Microsoft Defender ウィルス対策) です。

>:::image type="content" source ="images/network-protection-add-url-domain-indicator.png" alt-text="ネットワーク保護の追加 URL またはドメイン インジケーターを表示します。" lightbox="images/network-protection-add-url-domain-indicator.png":::

詳細については、「 [IP と URL/ドメインのインジケーターを作成する」を](indicator-ip-domain.md)参照してください。

### <a name="web-content-filtering"></a>Web コンテンツ フィルタリング

Web コンテンツ のフィルター処理は、Microsoft Defender for EndpointおよびMicrosoft Defender for Businessの [Web 保護機能](web-protection-overview.md)の一部です。 Web コンテンツ フィルターを使用すると、組織はコンテンツ カテゴリに基づいて Web サイトへのアクセスを追跡し、規制することができます。 これらの Web サイトの多く (悪意がない場合でも) は、コンプライアンス規制、帯域幅の使用、またはその他の懸念のために問題が発生する可能性があります。

特定のカテゴリをブロックするように、デバイス グループ間でポリシーを構成します。 カテゴリをブロックすると、指定したデバイス グループ内のユーザーがカテゴリに関連付けられている URL にアクセスできなくなります。 ブロックされていないカテゴリの場合、URL は自動的に監査されます。 ユーザーは中断することなく URL にアクセスでき、アクセス統計を収集して、よりカスタム ポリシーの決定を作成するのに役立ちます。 表示しているページ上の要素がブロックされたリソースを呼び出している場合、ユーザーにブロック通知が表示されます。

Web コンテンツ のフィルター処理は、主要な Web ブラウザーで利用できます。このブロックは、Windows Defender SmartScreen (Microsoft Edge) と Network Protection (Chrome、Firefox、Brave、Opera) によって実行されます。 ブラウザーのサポートの詳細については、「前提条件」を [参照してください](#prerequisites)。

> :::image type="content" source="images/network-protection-wcf-add-policy.png" alt-text="ネットワーク保護 Web コンテンツ フィルターの追加ポリシーを表示します。" lightbox="images/network-protection-wcf-add-policy.png":::

レポートの詳細については、「 [Web コンテンツ のフィルター処理](web-content-filtering.md)」を参照してください。

### <a name="microsoft-defender-for-cloud-applications"></a>Microsoft Defender for Cloud Applications

Microsoft Defender for Cloud Applications/ Cloud App Catalog では、エンドポイントのMicrosoft 365 Defenderを使用してアクセスするときにエンド ユーザーに警告を受け、_監視_ 対象としてマークするアプリを識別します。 監視対象アプリの下に一覧表示されているドメインは、後でエンドポイントのMicrosoft 365 Defenderに同期されます。

> :::image type="content" source="images/network-protection-macos-mcas-monitored-apps.png" alt-text="ネットワーク保護 mcas によって監視されるアプリを表示します。" lightbox="images/network-protection-macos-mcas-monitored-apps.png":::

10 ~ 15 分以内に、これらのドメインは、Endpoint Security Center のMicrosoft 365 Defenderの [インジケーター> URL/Domains with Action=Warn] の下に一覧表示されます。 適用 SLA 内 (この記事の最後にある詳細を参照)。

> :::image type="content" source="images/network-protection-macos-mcas-cloud-app-security.png" alt-text="ネットワーク保護 mcas クラウド アプリのセキュリティを示します。" lightbox="images/network-protection-macos-mcas-cloud-app-security.png":::

## <a name="see-also"></a>関連項目

- [ネットワークを保護する](network-protection.md)
- [ネットワーク保護を有効にする](enable-network-protection.md)
- [Web 保護](web-protection-overview.md)
- [インジケーターの作成](manage-indicators.md)
- [Web コンテンツ フィルタリング](web-content-filtering.md)
- [Linux 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-linux.md)
