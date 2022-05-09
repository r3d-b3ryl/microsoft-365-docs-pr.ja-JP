---
title: Microsoft Defender for Endpoint プラン 1 の概要
description: Defender for Endpoint プラン 1 の概要を確認します。 このエンドポイント保護サブスクリプションに含まれる機能と機能について説明します。
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: ITPro
ms.topic: overview
ms.date: 01/19/2022
ms.prod: m365-security
ms.technology: mdep1
ms.localizationpriority: medium
ms.reviewer: inbadian
f1.keywords: NOCSH
ms.collection:
- M365-security-compliance
- m365initiative-defender-endpoint
ms.custom: intro-overview
ms.openlocfilehash: 774d54aee080fbe3d6f5576fb29c85d887717b70
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/06/2022
ms.locfileid: "64663514"
---
# <a name="overview-of-microsoft-defender-for-endpoint-plan-1"></a>Microsoft Defender for Endpoint プラン 1 の概要

**適用対象**

- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)

Microsoft Defender for Endpointは、高度な脅威を防止、検出、調査、および対応できるように組織を支援するために設計されたエンタープライズ エンドポイント セキュリティ プラットフォームです。 Defender for Endpoint が 2 つのプランで利用できるようになったことをお知らせします。 

- この記事で説明する **Defender for Endpoint プラン 1**。そして 
- **[Defender for Endpoint Plan 2](microsoft-defender-endpoint.md)**(一般提供、以前は [Defender for Endpoint](microsoft-defender-endpoint.md) と呼ばられていました)。

次の図の緑色のボックスは、Defender for Endpoint プラン 1 に含まれる内容を示しています。

:::image type="content" source="../../media/mde-p1/mde-p1-overview-diagram.png" alt-text="Defender for Endpoint プラン 1 で得られた内容" lightbox="../../media/mde-p1/mde-p1-overview-diagram.png":::

このガイドを使用して、次の操作を行います。

- [Defender for Endpoint プラン 1 に含まれる内容の概要を確認する](#defender-for-endpoint-plan-1-capabilities)
- [Defender for Endpoint プラン 1 とプラン 2を比較する](defender-endpoint-plan-1-2.md)
- [Defender for Endpoint Plan 1 を設定して構成する方法について説明します](mde-p1-setup-configuration.md)
- [Microsoft 365 Defender ポータルを使用概要、インシデントとアラートの表示、デバイスの管理、検出された脅威に関するレポートの使用を行うことができます。](mde-plan1-getting-started.md)
- [メンテナンスと運用の概要を確認する](mde-p1-maintenance-operations.md)

> [!TIP]
> [Defender for Endpoint プラン 1 とプラン 2 の違いについて詳しく説明します](defender-endpoint-plan-1-2.md)。

## <a name="defender-for-endpoint-plan-1-capabilities"></a>Defender for Endpoint Plan 1 の機能

Defender for Endpoint Plan 1 には、次の機能が含まれています。

- 業界をリードする堅牢なマルウェア対策とウイルス対策の保護を含む **[次世代](#next-generation-protection)** の保護
- 脅威が検出されたときにセキュリティ チームがデバイスまたはファイルに対して実行できる手動 **[応答アクション](#manual-response-actions)** (ファイルの検疫への送信など)
- デバイスを強化し、ゼロデイ攻撃を防ぎ、エンドポイントのアクセスと動作をきめ細かく制御する攻撃 **[面の縮小機能](#attack-surface-reduction)**
- Microsoft 365 Defender ポータルを使用した **[一元的な構成と管理](#centralized-management)**、およびMicrosoft エンドポイント マネージャーとの統合
- Windows、macOS、iOS、Android デバイスなど、**[さまざまなプラットフォームの保護](#cross-platform-support)**

次のセクションでは、これらの機能について詳しく説明します。 

## <a name="next-generation-protection"></a>次世代の保護

次世代の保護には、堅牢なウイルス対策とマルウェア対策の保護が含まれます。 次世代の保護により、次の情報が得られます。 

- 動作ベース、ヒューリスティック、リアルタイムのウイルス対策保護 
- クラウドに配信された保護(新しい脅威と新しい脅威のほぼ瞬時の検出とブロックを含む) 
- Microsoft Defender ウイルス対策に関連する更新プログラムを含む、専用の保護と製品の更新 

詳細については、「 [次世代保護の概要](next-generation-protection.md)」を参照してください。

## <a name="manual-response-actions"></a>手動応答アクション

手動応答アクションは、エンドポイントまたはファイルで脅威が検出されたときにセキュリティ チームが実行できるアクションです。 Defender for Endpoint には、侵害された可能性がある、または疑わしいコンテンツがあると検出された [デバイスで実行できる特定の手動応答アクション](respond-machine-alerts.md) が含まれています。 脅威として検出された [ファイルに対して応答アクション](respond-file-alerts.md) を実行することもできます。 次の表は、Defender for Endpoint Plan 1 で使用できる手動応答アクションをまとめたものです。 <br/><br/>

| ファイル/デバイス | アクション | 説明 |
|:---|:---|:---|
| Device | ウイルス対策スキャンの実行 | ウイルス対策スキャンを開始します。 デバイスで脅威が検出された場合、多くの場合、ウイルス対策スキャン中にこれらの脅威に対処されます。 |
| Device | デバイスの分離 | Defender for Endpoint への接続を維持しながら、組織のネットワークからデバイスを切断します。 このアクションを使用すると、デバイスを監視し、必要に応じてさらにアクションを実行できます。 |
| ファイル | 停止と検疫 |プロセスの実行を停止し、関連付けられたファイルを検疫します。 |
| ファイル | ファイルをブロックまたは許可するインジケーターを追加する | ブロック インジケーターは、ポータブル実行可能ファイルがデバイスで読み取り、書き込み、または実行されないようにします。 <p>インジケーターを許可すると、ファイルがブロックまたは修復されなくなります。 |

詳細については、次の記事を参照してください。

- [デバイスで応答アクションを実行する](respond-machine-alerts.md) 
- [ファイルに対して応答アクションを実行する](respond-file-alerts.md)

## <a name="attack-surface-reduction"></a>攻撃面の縮小

組織の攻撃面は、サイバー攻撃に対して脆弱なすべての場所です。 Defender for Endpoint Plan 1 を使用すると、組織が使用するデバイスとアプリケーションを保護することで、攻撃面を減らすことができます。 Defender for Endpoint Plan 1 に含まれる攻撃面の縮小機能については、次のセクションで説明します。

- [攻撃面の減少ルール](#attack-surface-reduction-rules)
- [ランサムウェアの軽減策](#ransomware-mitigation)
- [デバイス コントロール](#device-control)
- [Web 保護](#web-protection)
- [ネットワーク保護](#web-protection)
- [ネットワーク ファイアウォール](#network-firewall)
- [アプリケーション制御](#application-control)

Defender for Endpoint の攻撃面削減機能の詳細については、 [攻撃面の縮小の概要](overview-attack-surface-reduction.md)に関するページを参照してください。

### <a name="attack-surface-reduction-rules"></a>攻撃面の減少ルール

攻撃表面の縮小ルールは、危険と見なされる特定のソフトウェア動作を対象とします。 このような動作は次のとおりです。

- 他のファイルをダウンロードまたは実行しようとする実行可能ファイルとスクリプトを起動する
- 難読化された、またはその他の疑わしいスクリプトの実行
- 通常の作業中にアプリが通常開始しない動作を開始する

正当なビジネス アプリケーションは、このようなソフトウェア動作を示す可能性があります。ただし、これらの動作は、マルウェアを介して攻撃者によって一般的に悪用されるため、リスクが高いと見なされることがよくあります。 攻撃面の縮小ルールは、危険な動作を制約し、組織を安全に保つのに役立ちます。

詳細については、「 [攻撃面の縮小ルールを使用してマルウェア感染を防ぐ」を](attack-surface-reduction.md)参照してください。

### <a name="ransomware-mitigation"></a>ランサムウェアの軽減策

フォルダー アクセスを制御すると、ランサムウェアの軽減策が得られます。 フォルダー アクセスを制御すると、信頼されたアプリのみがエンドポイント上の保護されたフォルダーにアクセスできます。 アプリは、その普及率と評判に基づいて、信頼できるアプリの一覧に追加されます。 セキュリティ運用チームは、信頼されたアプリの一覧からアプリを追加または削除することもできます。

詳細については、「 [フォルダー アクセスが制御された重要なフォルダーを保護する」を](controlled-folders.md)参照してください。

### <a name="device-control"></a>デバイス コントロール

組織のデバイスに対する脅威は、リムーバブル ドライブ (USB ドライブなど) 上のファイルの形式で行われることがあります。 Defender for Endpoint には、承認されていない周辺機器からの脅威がデバイスを侵害するのを防ぐのに役立つ機能が含まれています。 Defender for Endpoint を構成して、リムーバブル デバイス上のリムーバブル デバイスとファイルをブロックまたは許可できます。 

詳細については、「 [USB デバイスとリムーバブル メディアを制御](control-usb-devices-using-intune.md)する」を参照してください。

### <a name="web-protection"></a>Web 保護

Web 保護を使用すると、Web の脅威や不要なコンテンツから組織のデバイスを保護できます。 Web 保護には、Web 脅威の保護と Web コンテンツのフィルター処理が含まれます。

- [Web 脅威保護](web-threat-protection.md) により、フィッシング サイト、マルウェア ベクトル、悪用サイト、信頼されていないサイトまたは低評価のサイト、明示的にブロックしたサイトへのアクセスが防止されます。
- [Web コンテンツ フィルターを使用すると](web-content-filtering.md) 、カテゴリに基づいて特定のサイトにアクセスできなくなります。 カテゴリには、成人コンテンツ、娯楽サイト、法的責任サイトなどが含まれます。

詳細については、 [Web 保護](web-protection-overview.md)に関するページを参照してください。

### <a name="network-protection"></a>ネットワーク保護

ネットワーク保護を使用すると、フィッシング詐欺、悪用、その他の悪意のあるコンテンツをインターネット上でホストする可能性のある危険なドメインに組織がアクセスできないようにすることができます。 

詳細については、「 [ネットワークの保護](network-protection.md)」を参照してください。

### <a name="network-firewall"></a>ネットワーク ファイアウォール

ネットワーク ファイアウォール保護を使用すると、組織のデバイスとの間のフローが許可されているネットワーク トラフィックを決定するルールを設定できます。 Defender for Endpoint で得られるネットワーク ファイアウォールと高度なセキュリティを使用すると、次のことができます。

- ネットワーク セキュリティの脅威のリスクを軽減する
- 機密データと知的財産を保護する
- セキュリティへの投資を延長する

詳細については、「[高度なセキュリティを備えたファイアウォールWindows Defender](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security)」を参照してください。

### <a name="application-control"></a>アプリケーション制御

アプリケーション制御は、システム コア (カーネル) で信頼されたアプリケーションとコードのみを実行することで、Windows エンドポイントを保護します。 セキュリティ チームは、コード署名証明書、評判、起動プロセスなど、アプリケーションの属性を考慮するアプリケーション制御ルールを定義できます。 アプリケーション制御は、Windows 10 以降で使用できます。

詳細については、「[Windowsのアプリケーション コントロール」を](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control)参照してください。

## <a name="centralized-management"></a>集中管理

Defender for Endpoint Plan 1 には、Microsoft 365 Defender ポータルが含まれています。これにより、セキュリティ チームは検出された脅威に関する現在の情報を表示し、脅威を軽減するための適切なアクションを実行し、組織の脅威保護設定を一元的に管理できます。

詳細については、[ポータルの概要Microsoft 365 Defender](portal-overview.md)参照してください。

### <a name="role-based-access-control"></a>役割ベースのアクセス制御

ロールベースのアクセス制御 (RBAC) を使用して、セキュリティ管理者はロールとグループを作成して、Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) への適切なアクセスを許可できます。 RBAC を使用すると、Defender for Cloudにアクセスできるユーザーと、ユーザーが表示および実行できる操作をきめ細かく制御できます。 

詳細については、「 [ロールベースのアクセス制御を使用したポータル アクセスの管理](rbac.md)」を参照してください。

### <a name="reporting"></a>レポート

Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) では、検出された脅威に関する情報と、それらの脅威に対処するためのアクションに簡単にアクセスできます。 

- **ホーム** ページには、危険にさらされているユーザーまたはデバイス、検出された脅威の数、および作成されたアラート/インシデントを一目で表示するカードが含まれています。
- [ **インシデント&アラート** ] セクションには、トリガーされたアラートの結果として作成されたすべてのインシデントが一覧表示されます。 デバイス間で脅威が検出されると、アラートとインシデントが生成されます。
- **アクション センター** には、実行された修復アクションが一覧表示されます。 たとえば、ファイルが検疫に送信された場合、または URL がブロックされている場合、各アクションは [ **履歴** ] タブの [アクション センター] に一覧表示されます。
- [ **レポート]** セクションには、検出された脅威とその状態を示すレポートが含まれています。 

詳細については、「[Microsoft Defender for Endpoint プラン 1 の概要](mde-plan1-getting-started.md)」を参照してください。

### <a name="apis"></a>API

Defender for Endpoint API を使用すると、ワークフローを自動化し、組織のカスタム ソリューションと統合できます。 

詳細については、「 [Defender for Endpoint API」を](management-apis.md)参照してください。 

## <a name="cross-platform-support"></a>クロスプラットフォームサポート

ほとんどの組織では、さまざまなデバイスとオペレーティング システムが使用されます。 現在、Defender for Endpoint Plan 1 では、次のオペレーティング システムがサポートされています。

- Windows 7 (ESU が必要)
- Windows 8.1
- Windows 10バージョン 1709 以降
- macOS: 11.5 (Big Sur)、10.15.7 (Catalina)、または 10.14.6 (Mojave)
- iOS
- Android OS

## <a name="next-steps"></a>次の手順

- [Microsoft Defender for Endpoint プラン 1 とプラン 2 を比較する](defender-endpoint-plan-1-2.md)
- [Defender for Endpoint プラン 1 の設定と構成](mde-p1-setup-configuration.md)
- [Defender for Endpoint プラン 1 を使用した概要](mde-plan1-getting-started.md)
- [Defender for Endpoint プラン 1 の管理](mde-p1-maintenance-operations.md)
