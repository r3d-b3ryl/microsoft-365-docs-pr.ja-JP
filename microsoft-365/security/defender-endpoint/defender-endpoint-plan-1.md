---
title: Microsoft Defender for Endpoint Plan 1 の概要 (プレビュー)
description: Defender for Endpoint Plan 1 の概要を確認します。 このエンドポイント保護サブスクリプションに含まれる機能について説明します。
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: ITPro
ms.topic: overview
ms.date: 09/13/2021
ms.prod: m365-security
ms.technology: mdep1
localization_priority: Normal
ms.reviewer: inbadian
f1.keywords: NOCSH
ms.openlocfilehash: 74621e47b70e304afa70eb2e3513d5e6701afd0d
ms.sourcegitcommit: 4740e69326eb7f8302eec7bab5bd516d498e4492
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/16/2021
ms.locfileid: "59400308"
---
# <a name="overview-of-microsoft-defender-for-endpoint-plan-1-preview"></a>Microsoft Defender for Endpoint Plan 1 の概要 (プレビュー)

> [!TIP]
> プレビュー プログラムをMicrosoft 365 E3まだMicrosoft 365 E5場合は、プレビュー プログラムにサインアップ [https://aka.ms/mdep1trial](https://aka.ms/mdep1trial) してください。

Microsoft Defender for Endpoint は、高度な脅威を防止、検出、調査、および対応するための組織を支援するために設計されたエンタープライズ エンドポイント セキュリティ プラットフォームです。 Defender for Endpoint が次の 2 つのプランで利用可能になります。 

- **現在プレビュー中で、** この記事で説明されているエンドポイント プラン 1 の Defender。そして 
- **[Defender for Endpoint Plan 2](microsoft-defender-endpoint.md)**(一般提供)、以前は Defender for Endpoint と [呼ばれる](microsoft-defender-endpoint.md)。

次の図は、Defender for Endpoint Plan 1 (プレビュー) に含まれている情報を示しています。

:::image type="content" source="../../media/mde-p1/mde-p1-overview-diagram.png" alt-text="Defender for Endpoint Plan 1 ダイアグラム":::

このガイドを使用して、以下を行います。

- [Defender for Endpoint Plan 1 に含まれる機能の概要を確認する (プレビュー)](#defender-for-endpoint-plan-1-capabilities)
- [Defender for Endpoint プラン 1 とプラン 2を比較する](defender-endpoint-plan-1-2.md)
- [Defender for Endpoint Plan 1 をセットアップして構成する方法について説明します。](mde-p1-setup-configuration.md)
- [インシデントとアラートの表示、デバイスの管理、検出された脅威に関するレポートの使用が可能な Microsoft 365 Defender ポータルの使用を開始する](mde-plan1-getting-started.md)
- [メンテナンスと運用の概要を確認する](mde-p1-maintenance-operations.md)

> [!TIP]
> Defender for Endpoint Plan 1 と Plan 2 の違い[について詳しくは、以下をご覧ください](defender-endpoint-plan-1-2.md)。

## <a name="defender-for-endpoint-plan-1-capabilities"></a>Defender for Endpoint Plan 1 の機能

Defender for Endpoint Plan 1 (プレビュー) には、次の機能が含まれています。

- **[業界をリードする堅牢](#next-generation-protection)** なマルウェア対策とウイルス対策保護を含む次世代の保護
- **[脅威が検出された](#manual-response-actions)** 場合にセキュリティ チームがデバイスまたはファイルに対して実行できる、検疫にファイルを送信するなどの手動対応アクション
- **[デバイスを強化し、](#attack-surface-reduction)** ゼロデイ攻撃を防止し、エンドポイントのアクセスと動作を詳細に制御する攻撃表面の縮小機能
- **[サーバー ポータルとの一元](#centralized-management)** 的な構成と管理Microsoft 365 Defenderと統合Microsoft エンドポイント マネージャー
- **[さまざまなプラットフォームの](#cross-platform-support)** 保護 (Windows macOS、iOS、Android デバイスなど)

以下のセクションでは、これらの機能の詳細について説明します。 

> [!IMPORTANT]
> この記事の一部の情報は、製品リリース前に大幅に変更される可能性がある、事前リリース済みの製品/サービスに関連しています。 Microsoft は、ここに提供される情報について、明示または黙示を問わず一切の保証を行いません。 このガイドには、Defender for Endpoint Plan 1 (プレビュー) に含まれていない一部の機能を説明または表示する可能性があるオンライン コンテンツへのリンクが含まれています。

## <a name="next-generation-protection"></a>次世代の保護

次世代の保護には、堅牢なウイルス対策およびマルウェア対策保護が含まれます。 次世代の保護機能を使用すると、次の機能を利用できます。 

- 動作ベース、ヒューリスティック、リアルタイムのウイルス対策保護 
- 新しい脅威や新たな脅威のほぼ瞬時の検出とブロックを含む、クラウドによる保護 
- 製品に関連する更新プログラムを含む、専用の保護とMicrosoft Defender ウイルス対策 

詳細については、「次世代保護 [の概要」を参照してください](next-generation-protection.md)。

## <a name="manual-response-actions"></a>手動応答アクション

手動対応アクションは、エンドポイントまたはファイルで脅威が検出された場合にセキュリティ チームが実行できるアクションです。 Defender for Endpoint には [、侵害の](respond-machine-alerts.md) 可能性がある、または疑わしいコンテンツが含まれると検出されたデバイスで実行できる特定の手動応答アクションが含まれます。 脅威として検出 [されたファイルに](respond-file-alerts.md) 対して応答アクションを実行することもできます。 次の表に、Defender for Endpoint Plan 1 で使用できる手動応答アクションの概要を示します。 <br/><br/>

| ファイル/デバイス | アクション | 説明 |
|:---|:---|:---|
| デバイス | ウイルス対策スキャンの実行 | ウイルス対策スキャンを開始します。 デバイスで脅威が検出された場合、ウイルス対策スキャン中にこれらの脅威に対処する場合が多い。 |
| デバイス | デバイスの分離 | Defender for Endpoint への接続を維持しながら、組織のネットワークからデバイスを切断します。 このアクションを使用すると、デバイスを監視し、必要に応じてさらにアクションを実行できます。 |
| ファイル | 停止と検疫 |プロセスの実行を停止し、関連ファイルを検疫します。 |
| ファイル | ファイルをブロックまたは許可するインジケーターを追加する | ブロックインジケーターは、ポータブル実行可能ファイルがデバイスで読み取り、書き込み、または実行されるのを防ぐ。 <p>許可インジケーターは、ファイルがブロックまたは修復されるのを防ぐ。 |

詳細については、次の記事を参照してください。

- [デバイスで応答アクションを実行する](respond-machine-alerts.md) 
- [ファイルに対する応答アクションの実行](respond-file-alerts.md)

## <a name="attack-surface-reduction"></a>攻撃面の縮小

組織の攻撃表面は、サイバー攻撃に対して脆弱なすべての場所です。 Defender for Endpoint Plan 1 (プレビュー) を使用すると、組織で使用するデバイスとアプリケーションを保護することで、攻撃の表面を軽減できます。 Defender for Endpoint Plan 1 (プレビュー) に含まれる攻撃表面の縮小機能については、以下のセクションで説明します。

- [攻撃面の減少ルール](#attack-surface-reduction-rules)
- [ランサムウェアの軽減](#ransomware-mitigation)
- [デバイス コントロール](#device-control)
- [Web 保護](#web-protection)
- [ネットワーク保護](#web-protection)
- [ネットワーク ファイアウォール](#network-firewall)
- [アプリケーション制御](#application-control)

Defender for Endpoint の攻撃表面縮小機能の詳細については、「攻撃表面の縮小の [概要」を参照してください](overview-attack-surface-reduction.md)。

### <a name="attack-surface-reduction-rules"></a>攻撃面の減少ルール

攻撃表面の縮小ルールは、リスクが高いと見なされる特定のソフトウェア動作を対象とします。 このような動作には、次のものが含まれます。

- 他のファイルをダウンロードまたは実行しようとする実行可能ファイルとスクリプトの起動
- 難読化されたスクリプトまたはその他の疑わしいスクリプトを実行する
- 通常の作業中にアプリが通常開始しない動作を開始する

正当なビジネス アプリケーションは、このようなソフトウェア動作を示す可能性があります。ただし、これらの動作は、マルウェアを介して攻撃者によって悪用されるのが一般的なので、リスクが高いと見なされる場合が多い。 攻撃表面の縮小ルールは、リスクの高い動作を制限し、組織を安全に保つのに役立ちます。

詳細については、「攻撃表面の [縮小ルールを使用してマルウェアの感染を防ぐ」を参照してください](attack-surface-reduction.md)。

### <a name="ransomware-mitigation"></a>ランサムウェアの軽減

フォルダー アクセスを制御すると、ランサムウェアの軽減を受け取る。 フォルダー アクセスの制御により、信頼できるアプリだけがエンドポイント上の保護されたフォルダーにアクセスできます。 アプリは、その普及率と評判に基づいて信頼できるアプリの一覧に追加されます。 セキュリティ運用チームは、信頼できるアプリの一覧からアプリを追加または削除することもできます。

詳細については、「フォルダー アクセスを [制御して重要なフォルダーを保護する」を参照してください](controlled-folders.md)。

### <a name="device-control"></a>デバイス コントロール

組織のデバイスに対する脅威は、USB ドライブなどのリムーバブル ドライブ上のファイルの形式で受け取る場合があります。 Defender for Endpoint には、承認されていない周辺機器からの脅威がデバイスを侵害するのを防ぐための機能が含まれています。 Defender for Endpoint を構成して、リムーバブル デバイス上のリムーバブル デバイスとファイルをブロックまたは許可できます。 

詳細については [、「Control USB デバイスとリムーバブル メディア」を参照してください](control-usb-devices-using-intune.md)。

### <a name="web-protection"></a>Web 保護

Web 保護を使用すると、Web の脅威や望ましくないコンテンツから組織のデバイスを保護できます。 Web 保護には、Web 脅威保護と Web コンテンツ フィルターが含まれます。

- [Web 脅威保護は](web-threat-protection.md) 、フィッシング サイト、マルウェア ベクター、悪用サイト、信頼されていないサイトまたは低評価サイト、および明示的にブロックするサイトへのアクセスを防止します。
- [Web コンテンツ フィルター](web-content-filtering.md) (プレビュー) では、カテゴリに基づいて特定のサイトにアクセスできません。 カテゴリには、アダルト コンテンツ、レジャー サイト、法的責任サイトなどがあります。

詳細については、「Web 保護」 [を参照してください](web-protection-overview.md)。

### <a name="network-protection"></a>ネットワーク保護

ネットワーク保護を使用すると、フィッシング詐欺、悪用、その他の悪意のあるコンテンツをインターネット上でホストする可能性のある危険なドメインに組織がアクセスするのを防ぐことが可能です。 

詳細については、「ネットワークの保護 [」を参照してください](network-protection.md)。

### <a name="network-firewall"></a>ネットワーク ファイアウォール

ネットワーク ファイアウォール保護を使用すると、組織のデバイスとの間で流れるネットワーク トラフィックを決定するルールを設定できます。 Defender for Endpoint で取得するネットワーク ファイアウォールと高度なセキュリティを使用すると、次の機能を使用できます。

- ネットワーク セキュリティの脅威のリスクを軽減する
- 機密データと知的財産を保護する
- セキュリティ投資の拡張

詳細については、「高度なセキュリティ[を備Windows Defenderファイアウォール」を参照してください](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security)。

### <a name="application-control"></a>アプリケーション制御

アプリケーション制御は、システム Windows (カーネル) で信頼できるアプリケーションとコードのみを実行することで、アプリケーション エンドポイントを保護します。 セキュリティ チームは、アプリケーションの属性 (証明書の共同設計、評判、起動プロセスなど) を考慮するアプリケーション制御ルールを定義できます。 アプリケーションコントロールは、Windows 10以降で使用できます。

詳細については、「アプリケーション コントロール[for Windows」 を参照してください](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control)。

## <a name="centralized-management"></a>集中管理

Defender for Endpoint Plan 1 (プレビュー) には Microsoft 365 Defender ポータルが含まれています。これにより、セキュリティ チームは検出された脅威に関する現在の情報を表示し、脅威を軽減するための適切なアクションを実行し、組織の脅威保護設定を一本的に管理できます。

詳細については、「ポータルの概要[Microsoft 365 Defender」を参照してください](portal-overview.md)。

### <a name="role-based-access-control"></a>役割ベースのアクセス制御

役割ベースのアクセス制御 (RBAC) を使用して、セキュリティ管理者は役割とグループを作成して、管理者ポータル () への適切なアクセスをMicrosoft 365 Defenderできます [https://security.microsoft.com](https://security.microsoft.com) 。 RBAC を使用すると、セキュリティ センターにアクセスできるユーザーと、セキュリティ センターにアクセスできるユーザーの表示と操作を詳細に制御できます。 

詳細については、「役割ベースのアクセス [制御を使用してポータル アクセスを管理する」を参照してください](rbac.md)。

### <a name="reporting"></a>レポート

このMicrosoft 365 Defenderポータル ( ) は、検出された脅威に関する情報や、それらの脅威に対処するアクション [https://security.microsoft.com](https://security.microsoft.com) に簡単にアクセスできます。 

- ホーム **ページには** 、危険にさらされているユーザーまたはデバイス、検出された脅威の数、作成されたアラート/インシデントを一目で示すカードが含まれています。
- [ **インシデントと&] セクション** には、トリガーされたアラートの結果として作成されたインシデントが一覧表示されます。 アラートとインシデントは、デバイス間で脅威が検出されると生成されます。
- アクション **センターには、** 実行された修復アクションが一覧表示されます。 たとえば、ファイルが検疫に送信された場合、または URL がブロックされている場合、各アクションは [履歴] タブの [アクション センター] に **一覧表示** されます。
- [ **レポート] セクション** には、検出された脅威とその状態を示すレポートが含まれています。 

詳細については [、「Microsoft Defender for Endpoint Plan 1 の概要 (プレビュー)」を参照してください](mde-plan1-getting-started.md)。

### <a name="apis"></a>API

Defender for Endpoint API を使用すると、ワークフローを自動化し、組織のカスタム ソリューションと統合できます。 

詳細については [、「Defender for Endpoint API」を参照してください](management-apis.md)。 

## <a name="cross-platform-support"></a>クロスプラットフォームのサポート

ほとんどの組織では、さまざまなデバイスとオペレーティング システムを使用しています。 現在、Defender for Endpoint Plan 1 (プレビュー) は次のオペレーティング システムをサポートしています。

- Windows 10バージョン 1709 以降
- macOS: 11.5 (Big Sur), 10.15.7 (Catalina), or 10.14.6 (Mojave)
- iOS
- Android OS

## <a name="next-steps"></a>次の手順

- [Microsoft Defender for Endpoint Plan 1 (プレビュー) とプラン 2 の比較](defender-endpoint-plan-1-2.md)
- [Defender for Endpoint Plan 1 のセットアップと構成 (プレビュー)](mde-p1-setup-configuration.md)
- [Defender for Endpoint Plan 1 の概要 (プレビュー)](mde-plan1-getting-started.md)
- [エンドポイント プラン 1 の Defender の管理 (プレビュー)](mde-p1-maintenance-operations.md)