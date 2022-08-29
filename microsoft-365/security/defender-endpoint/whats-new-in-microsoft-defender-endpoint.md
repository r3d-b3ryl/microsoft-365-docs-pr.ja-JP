---
title: Microsoft Defender for Endpoint の新機能
description: Microsoft Defender for Endpointの最新リリースで一般公開されている機能 (GA) と、Windows 10と Windows Server のセキュリティ機能について説明します。
keywords: Microsoft Defender for Endpoint、ga、一般公開、機能、利用可能、新規の新機能
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: secure
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
ms.date: 08/25/2022
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 07f9aa517ae0cc4b442d0296df82f219e242debf
ms.sourcegitcommit: 6f565d9e0f91ebc76fd13d7005619531391ab5f9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2022
ms.locfileid: "67439610"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpoint の新機能

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**

- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-pullalerts-abovefoldlink)

次の機能は、Microsoft Defender for Endpointの最新リリースでプレビュー段階または一般公開 (GA) されています。

プレビュー機能の詳細については、「 [プレビュー機能](preview.md)」を参照してください。

> [!TIP]
> RSS フィード: ご自身のフィード リーダーに次の URL をコピーして貼り付けると、このページの更新時に通知を受け取ることができます。
>
> ```https
> https://docs.microsoft.com/api/search/rss?search=%22features+are+generally+available+%28GA%29+in+the+latest+release+of+Microsoft+Defender+for+Endpoint%22&locale=en-us&facet=
> ```

他の Microsoft Defender セキュリティ製品の新機能の詳細については、次を参照してください。

- [Microsoft 365 Defender の新機能](../defender/whats-new.md)
- [Microsoft Defender for Office 365 の新機能](../office-365-security/whats-new-in-defender-for-office-365.md)
- [Microsoft Defender for Identityの新機能](/defender-for-identity/whats-new)
- [Microsoft Cloud App Securityの新機能](/cloud-app-security/release-notes)

他のオペレーティング システムでのMicrosoft Defender for Endpointの詳細については、次の手順を参照してください。

- [macOS 上の Defender for Endpoint の新機能](mac-whatsnew.md)
- [iOS 上の Defender for Endpoint の新機能](ios-whatsnew.md)
- [Defender for Endpoint on Linux の新機能](linux-whatsnew.md)

## <a name="august-2022"></a>2022 年 8 月

- [デバイスの正常性の状態](investigate-machines.md#device-health-status)<br>デバイスの正常性状態カードには、特定のデバイスの正常性レポートの概要が表示されます。
- [デバイス正常性レポート (プレビュー)](/microsoft-365/security/defender-endpoint/machine-reports)<br> デバイスの状態レポートには、組織内のデバイスに関する高度な情報が表示されます。 このレポートには、センサーの正常性状態、ウイルス対策状態、OS プラットフォーム、およびWindows 10バージョンを示す傾向のある情報が含まれています。
- [macOS での改ざん防止が一般公開されました](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/tamper-protection-on-macos-is-now-generally-available/ba-p/3595422)<br> この機能は、既定で監査モードが有効になっている状態でリリースされ、機能を強制 (ブロック) するかオフにするかを決定できます。 今年の後半には、エンドポイントをブロック モードに自動的に切り替える段階的なロールアウト メカニズムを提供します。これは、機能を有効 (ブロック モード) または無効にする選択を特に行っていない場合にのみ適用されることに注意してください。
- [macOS と Linux 用の Network Protection と Web Protection がパブリック プレビューになりました。](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/network-protection-and-web-protection-for-macos-and-linux-is-now/ba-p/3601576)<br>Network Protection は、インターネット ベースのイベントからデバイスの攻撃面を減らすのに役立ちます。 これにより、従業員がアプリケーションを使用して、フィッシング詐欺、悪用、その他の悪意のあるコンテンツをインターネット上でホストする可能性のある危険なドメインにアクセスできなくなります。 これは、Web Protection for Microsoft Defender for Endpointが構築される基盤です。 これらの機能には、Web 脅威保護、Web コンテンツ フィルタリング、IP/URL カスタム インジケーターが含まれます。 Web 保護を使用すると、Web の脅威からデバイスを保護し、不要なコンテンツを規制するのに役立ちます。
- [Windows Server 2012 R2 およびWindows Server 2016のMicrosoft Defender for Endpoint (MDE) オンボードの改善](/mem/configmgr/core/plan-design/changes/whats-new-in-version-2207#improved-microsoft-defender-for-endpoint-mde-onboarding-for-windows-server-2012-r2-and-windows-server-2016)<br>Configuration Manager バージョン 2207 では、Windows Server 2012 R2 & 2016 の最新の統合Microsoft Defender for Endpointの自動展開がサポートされるようになりました。 Microsoft Defender for Endpointオンボード ポリシーを対象とするWindows Server 2012デバイスと 2016 デバイスでは、クライアント設定を使用して構成されている場合、統合エージェントと既存の Microsoft Monitoring Agent ベースのソリューションが使用されます。


## <a name="july-2022"></a>2022 年 7 月
- [ドメイン コントローラー デバイスの追加 - 評価ラボの機能強化](evaluation-lab.md#add-a-domain-controller)<br>一般提供開始 - ドメイン コントローラーを追加して、複数のデバイス間での横移動や多段階攻撃などの複雑なシナリオを実行します。
- [Microsoft Defender for Endpointでファイル ページの機能強化を発表する](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/announcing-file-page-enhancements-in-microsoft-defender-for/ba-p/3584004)<br>Microsoft Defender for Endpointでファイルを調査したことがありますか? ファイル ページとサイド パネルの機能強化が最近発表され、さらに簡単になりました。 ユーザーは、この情報をすべて 1 か所でホストする、より効率的なナビゲーション エクスペリエンスを実現することで、プロセスを効率化できるようになりました。
- [新しいアラート抑制エクスペリエンスの概要](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/introducing-the-new-alert-suppression-experience/ba-p/3562719)<br>新しい高度なアラート抑制エクスペリエンスが一般公開されました。 新しいエクスペリエンスにより、細分性と制御が強化され、ユーザーはMicrosoft Defender for Endpointアラートを調整できます。
- [侵害されたアンマネージド デバイスが組織内で横に移動しないようにするには、次の操作を行います。](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/prevent-compromised-unmanaged-devices-from-moving-laterally-in/ba-p/3482134)<br>今日から、Microsoft Defender for Endpointに登録されていないデバイスが侵害されている疑いがある場合は、SOC アナリストとして"含める" ことができるようになります。 その結果、Microsoft Defender for Endpointに登録されたすべてのデバイスが、疑わしいデバイスとの送受信通信をブロックするようになりました。
- [Defender for Endpoint を使用する米国政府機関のお客様は、モバイル デバイスのサポートを利用できるようになりました](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/mobile-device-support-is-now-available-for-us-government/ba-p/3472590)<br>米国政府機関のお客様向けのMicrosoft Defender for Endpointは、Azure US Government 環境に組み込まれており、Azure Commercial の Defender と同じ基になるテクノロジを使用します。 このオファリングは GCC、GCC High、DoD のお客様が利用でき、Windows、MacOS、Linux から Android および iOS デバイスへのプラットフォームの可用性をさらに拡張します。


## <a name="june-2022"></a>2022 年 6 月
- [Defender for Servers プラン 2 が MDE 統合ソリューションと統合されるようになりました](https://techcommunity.microsoft.com/t5/microsoft-defender-for-cloud/defender-for-servers-plan-2-now-integrates-with-mde-unified/ba-p/3527534)<br>これで、Windows Server 2012 R2 と 2016 の最新の統合ソリューションを、1 つのボタンを使用して Defender for Servers Plan 2 の対象となるサーバーに展開できるようになりました。
- [Android & iOS 上のMicrosoft Defender for Endpointのモバイル ネットワーク保護がパブリック プレビューに追加されました](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/mobile-network-protection-in-microsoft-defender-for-endpoint-on/ba-p/3559121)<br>Microsoft は Defender for Endpoint のモバイル ネットワーク保護機能を提供しており、組織は堅牢な脅威インテリジェンスを利用してエンドポイントの弱点を特定、評価、修復するのに役立ちます。 Microsoft Defender for Endpointを使用して、Android プラットフォームと iOS プラットフォームの両方でこの新機能の恩恵を受けられることをお知らせします。

## <a name="may-2022"></a>2022 年 5 月
- [macOS の改ざん防止 (プレビュー)](tamperprotection-macos.md)<br>改ざん防止は、macOS でのMicrosoft Defender for Endpointの不正な削除を防ぐのに役立ちます。
- [ドメイン コントローラー デバイスの追加 - 評価ラボの機能強化 (プレビュー)](evaluation-lab.md#add-a-domain-controller)<br>ドメイン コントローラーを追加して、複数のデバイスにわたる横移動や多段階攻撃などの複雑なシナリオを実行します。
- [Microsoft Defender for Endpointのトラブルシューティング モードが一般公開されました](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/troubleshooting-mode-for-microsoft-defender-for-endpoint-now/ba-p/3347344)<br>トラブルシューティング モードの概要。デバイスの構成を調査して調整するための、革新的で安全な独自の方法です。 このモードでは、デバイス上のローカル管理者が、改ざん防止を含め、デバイス上の Microsoft Defender ウイルス対策セキュリティ ポリシー構成をオーバーライドできるようになります。 
- [Android Enterprise 用 Defender for Endpoint 個人用プロファイルのパブリック プレビューを発表する](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/announcing-the-public-preview-of-defender-for-endpoint-personal/ba-p/3370979)<br>職場の BYOD プログラムに自分のデバイスを登録したいユーザーが、個人プロファイルでMicrosoft Defender for Endpointによって提供される保護の恩恵を受けられるようになったことをお知らせします。
- [Microsoft Defender for Endpointのセキュリティ設定管理が一般公開されました](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/security-settings-management-in-microsoft-defender-for-endpoint/ba-p/3356970)<br>2021 年後半に、Microsoft Defender for Endpoint構成管理機能が拡張されたことを発表しました。 このリリースでは、セキュリティ チームは、追加のツールやインフラストラクチャを展開して実装することなく、必要なセキュリティ設定でデバイスを構成できるようになりました。  Microsoft エンドポイント マネージャーで可能になった組織は、参加しているすべてのデバイスについて、ウイルス対策 (AV)、エンドポイント検出と応答 (EDR)、ファイアウォール (FW) ポリシーを 1 つのビューから管理できるようになりました。 現在、この機能は Windows クライアントと Windows サーバーで一般公開され、Windows 10、Windows 11、Windows Server 2012 R2 以降がサポートされるようになりました。

## <a name="april-2022"></a>2022 年 4 月
- [Windows Server 2012 R2 とWindows Server 2016) のオンボードと機能パリティを更新しました](configure-server-endpoints.md)<br/> 新しい統合ソリューション パッケージが一般公開され、依存関係とインストール手順を削除することで、サーバーのオンボードが容易になりました。 さらに、この統合ソリューション パッケージには、多くの新機能が追加されています。
- [iOS 用 Tunnel との統合](https://techcommunity.microsoft.com/t5/microsoft-endpoint-manager-blog/what-s-new-in-microsoft-endpoint-manager-2204-april-edition/ba-p/3297995)。 iOS のMicrosoft Defender for Endpointは、1 つのアプリでセキュリティと接続を有効にする VPN ゲートウェイ ソリューションである Microsoft Tunnel と統合できるようになりました。 この機能は、以前は Android でのみ使用できます。
- [Microsoft Defender for Endpoint Android でのマルウェア対策の強化](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/enhanced-antimalware-protection-in-microsoft-defender-for/ba-p/3290320)<br>Android 上のMicrosoft Defender for Endpointのマルウェア保護機能に関する主要な更新プログラムを共有できることを楽しみにしています。 これらの新機能は、Microsoft Defender for Endpointにおける次世代の保護の主要なコンポーネントを形成します。 この保護により、機械学習、ビッグ データ分析、詳細な脅威調査、Microsoft クラウド インフラストラクチャがまとめられ、組織内の Android デバイス (またはエンドポイント) が保護されます。
- [Linux と macOS 用のマルウェア対策エンジン機能の強化](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/enhanced-antimalware-engine-capabilities-for-linux-and-macos/ba-p/3292003)<br>新しい強化されたエンジンを使用して、Linux および macOS での次世代保護への大幅なアップグレードを発表します。 Microsoft Defender ウイルス対策マルウェア対策エンジンは、次世代の保護の重要なコンポーネントです。 この保護により、機械学習、ビッグ データ分析、詳細な脅威調査、Microsoft クラウド インフラストラクチャが実現し、組織内のデバイス (またはエンドポイント) を保護できます。 このメジャー 更新プログラムの主な利点には、パフォーマンスと防止の強化、および macOS および Linux でのカスタム ファイル インジケーターのサポートの追加が含まれます。
- [デバイス制御とWindows Defenderファイアウォールの新しいレポート機能](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/new-reporting-functionality-for-device-control-and-windows/ba-p/3290601)<br>Microsoft 365 Defender ポータル内で新しいエンドポイント レポート機能をお知らせします。 この作業により、新しいエンドポイント レポートがまとめられます。これにより、数回クリックするだけで環境内で何が起こっているかを確認できます。 Microsoft のレポートは、デバイスの動作とアクティビティに関する分析情報を提供する一方で、デバイスのタイムラインや高度な捜索など、Microsoft 365 Defender ポータル内の統合エクスペリエンスを最大限に活用できるように設計されています。
- [Microsoft 365 Defenderの統合された申請が一般公開されました。](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/unified-submissions-in-microsoft-365-defender-now-generally/ba-p/3270770)<br>セキュリティ チームに、メール、URL、電子メールの添付ファイル、ファイルを 1 つの使いやすい送信エクスペリエンスで送信するための"ワン ストップ ショップ" が追加されました。 提出プロセスを簡略化するために、Microsoft 365 Defender ポータル (https://security.microsoft.com). 統合された提出では、ポータル内からレビューのためにファイルをMicrosoft 365 Defenderに送信できます。 また、Microsoft Defender for Endpointアラート ページからファイルを直接送信する機能も追加されています。  
- [Live Response API の拡張されたサポートと機能の発表](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/announcing-expanded-support-and-functionality-for-live-response/ba-p/3178432)<br>Microsoft Defender for Endpointでサポートされているすべてのプラットフォームで既存の API のサポートを引き続き拡大し、組織の応答の自動化とオーケストレーションの簡素化と強化に役立つ新しい API を発表することをお知らせします。

## <a name="february-2022"></a>2022 年 2 月

- [Microsoft Security 用 Splunk アドオンが利用可能になりました](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/the-splunk-add-on-for-microsoft-security-is-now-available/ba-p/3171272)<br>Splunk でサポートされている Microsoft Security 用 Splunk アドオンが利用可能になりました。 このアドオンは、Splunk 1.3.0 用のMicrosoft 365 Defender アドオンに基づいて構築され、Microsoft Defender for Endpoint Alerts API プロパティまたはMicrosoft 365 Defender Incidents API プロパティを Splunk の共通情報モデル (CIM) にマップします。
- [レガシ SIEM API の非推奨 - 延期](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/deprecating-the-legacy-siem-api-postponed/ba-p/3139643)<br>SIEM REST API は 2022 年 4 月 1 日に非推奨になると以前に発表しました。 お客様からのフィードバックに耳を傾け、API の廃止は今のところ延期されました。詳細については、2022 年第 3 四半期に予定されています。 2022 年第 3 四半期に Microsoft Graph でMicrosoft 365 Defender API に関する魅力的な詳細を共有することを楽しみにしています。

## <a name="january-2022"></a>2022 年 1 月

- [Android と iOS の脆弱性管理が一般公開されました](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/announcing-general-availability-of-vulnerability-management/ba-p/3071663)<br>この新しいクロスプラットフォーム カバレッジにより、脅威と脆弱性の管理機能は、ワークステーション、サーバー、モバイル デバイスにまたがる組織全体のすべての主要なデバイス プラットフォームをサポートするようになりました。 
- [M365 E3/A3 ライセンスに含まれるMicrosoft Defender for Endpointプラン 1](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/microsoft-defender-for-endpoint-plan-1-now-included-in-m365-e3/ba-p/3060639)<br>1 月 14 日以降、Microsoft Defender for Endpoint プラン 1 (P1) はMicrosoft 365 E3/A3 ライセンスに自動的に含まれます。
- [iOS でのMicrosoft Defender for Endpointのゼロタッチオンボードがパブリック プレビューになりました](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/zero-touch-onboarding-of-microsoft-defender-for-endpoint-on-ios/ba-p/3038045)<br>この新しい機能により、企業は、エンド ユーザーがアプリを操作しなくても、Microsoft エンドポイント マネージャーに自動的に登録されている iOS デバイスにMicrosoft Defender for Endpointを展開できるようになりました。 これにより、展開の摩擦が軽減され、対象デバイスでサイレント アクティブ化され、iOS 資産の保護が開始Microsoft Defender for Endpoint、すべてのデバイスにアプリを展開するために必要な時間が大幅に短縮されます。

## <a name="december-2021"></a>2021 年 12 月

- [Microsoft Defender 脆弱性の管理は、アプリケーションとコンポーネントの Log4j の脆弱性を特定するのに役立ちます](https://www.microsoft.com/security/blog/2021/12/11/guidance-for-preventing-detecting-and-hunting-for-cve-2021-44228-log4j-2-exploitation/#TVM)<br>脅威と脆弱性の管理は、Log4j の脆弱性と環境内の関連するリスクの影響を受けるデバイスを自動的かつシームレスに識別し、軽減する時間を大幅に短縮します。 Microsoft は、脅威の状況からの最新情報に基づいて、これらの機能を繰り返し処理し続けます。
- IoT デバイスの検出 (プレビュー): [デバイス検出](device-discovery.md) は、企業ネットワークに接続されているアンマネージド IoT デバイスを見つけるのに役立つようになりました。 これにより、他の IT デバイス (ワークステーション、サーバー、モバイル) と共に IoT インベントリを 1 つの統合ビューで表示できます。
- [Microsoft Defender for IoT 統合 (プレビュー)](enable-microsoft-defender-for-iot-integration.md): この統合により、Microsoft Defender for IoT によって提供されるエージェントレス監視機能を使用して、デバイス検出機能が強化されます。 これにより、ネットワーク内の IoT デバイスの特定、識別、セキュリティ保護に役立つ可視性が向上します。

## <a name="november-2021"></a>2021 年 11 月

- [セキュリティ構成管理](security-config-management.md) <br/> Microsoft エンドポイント マネージャーによって管理されていないデバイス (Microsoft Intuneまたは Microsoft Endpoint Configuration Manager) が Microsoft Defender のセキュリティ構成をエンドポイント マネージャーから直接受信する機能。
- [評価ラボ: 展開された OS サポート & Atomic Red Team シミュレーション](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/evaluation-lab-expanded-os-support-amp-atomic-red-team/ba-p/2993927)<br>評価ラボでは、Windows 11、Windows Server 2016、Linux デバイスの追加がサポートされるようになりました。 さらに、Red Canary のオープンソース シミュレーション ライブラリである Atomic Red Team との新しいパートナーシップも発表したいと思います。
- [Microsoft Defender for Endpoint Mobile - 改ざん防止のパブリック プレビューの発表](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/announcing-the-public-preview-of-microsoft-defender-for-endpoint/ba-p/2971038)<br>Microsoft Defender for Endpoint モバイル アプリで 7 日間非アクティブ状態の後、デバイスを非準拠としてマークします。
- [動作監視、拡張されたディストリビューション カバレッジなどを使用して Linux 資産の保護を強化する](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/boost-protection-of-your-linux-estate-with-behavior-monitoring/ba-p/2909320)<br>Linux の次世代の保護、エンドポイントの検出と応答 (EDR)、脅威と脆弱性の管理 (TVM) に関するMicrosoft Defender for Endpointに関する最新のニュースを共有できます。 お使いの Linux 資産に対する Microsoft の保護は、セキュリティ スイート全体で大きく向上しています。 Linux の Azure Security Center への統合に関する最近のMicrosoft Defender for Endpointにより、Linux EDR と TVM の利点は Azure Defender のお客様にも広がっています。

## <a name="october-2021"></a>2021 年 10 月

- [Windows Server 2012 R2 とWindows Server 2016のオンボードと機能パリティを更新しました (プレビュー)](configure-server-endpoints.md)<br/> 新しい統合ソリューション パッケージでは、依存関係とインストール手順を削除することで、サーバーのオンボードが容易になります。 さらに、この統合ソリューション パッケージには、多くの新機能が追加されています。
- Microsoft Defender for EndpointとMicrosoft 365 DefenderにWindows 11サポートが追加されました。

## <a name="september-2021"></a>2021 年 9 月

- [Web コンテンツ フィルタリング](web-content-filtering.md) <br/>Microsoft Defender for Endpointの Web 保護機能の一環として、Web コンテンツ フィルターを使用すると、組織のセキュリティ チームは、コンテンツ カテゴリに基づいて Web サイトへのアクセスを追跡および規制できます。 カテゴリには、成人用コンテンツ、高帯域幅、法的責任、娯楽、分類されていないものなどがあります。 これらのカテゴリの 1 つ以上に分類される多くの Web サイトは悪意がない可能性がありますが、コンプライアンス規制、帯域幅の使用、またはその他の懸念のために問題が発生する可能性があります。 [Web コンテンツ のフィルター処理の詳細について説明します](web-content-filtering.md)。

## <a name="august-2021"></a>2021 年 8 月

- (プレビュー)[Microsoft Defender for Endpoint プラン 1 ](defender-endpoint-plan-1.md) <br/>Defender for Endpoint Plan 1 (プレビュー) は、次世代の保護、攻撃面の削減、一元管理とレポート、API を含むエンドポイント保護ソリューションです。 Defender for Endpoint Plan 1 (プレビュー) は、エンドポイント保護機能を試したい、Microsoft 365 E3を持ち、まだMicrosoft 365 E5していないお客様向けの新しいオファリングです。 

   詳細については、「[Microsoft Defender for Endpoint プラン 1 (プレビュー)](defender-endpoint-plan-1.md)」を参照してください。 既存の [Defender for Endpoint](microsoft-defender-endpoint.md) 機能は、Defender for Endpoint プラン 2 と呼ばれます。 
- (プレビュー) [Web コンテンツ フィルター](web-content-filtering.md)<br>  Web コンテンツ のフィルター処理は、Microsoft Defender for Endpointの Web 保護機能の一部です。 これにより、組織は、コンテンツ カテゴリに基づいて Web サイトへのアクセスを追跡し、規制することができます。 これらの Web サイトの多くは、悪意はありませんが、コンプライアンス規制、帯域幅の使用、またはその他の懸念のために問題が発生する可能性があります。

## <a name="july-2021"></a>2021 年 7 月

- (プレビュー) [デバイスの正常性とコンプライアンス レポート](machine-reports.md) <br>  デバイスの正常性とコンプライアンス レポートには、組織内のデバイスに関する高度な情報が表示されます。

## <a name="june-2021"></a>2021 年 6 月

- [Delta Export ソフトウェアの脆弱性評価](get-assessment-methods-properties.md#31-methods) Api <br> [脆弱性とセキュリティで保護された構成 API コレクションのエクスポート評価に](get-assessment-methods-properties.md)加えて。 <br> 完全なソフトウェア脆弱性評価 (JSON 応答) とは異なり、これは、デバイス別に組織のソフトウェア脆弱性評価のスナップショット全体を取得するために使用されます。差分エクスポート API 呼び出しは、選択した日付と現在の日付 ("delta" API 呼び出し) の間に発生した変更のみをフェッチするために使用されます。 毎回大量のデータを含む完全なエクスポートを取得する代わりに、新しい脆弱性、修正された脆弱性、更新された脆弱性に関する特定の情報のみを取得します。 Delta export API 呼び出しを使用して、「修正された脆弱性の数」や「組織に追加された新しい脆弱性の数」など、さまざまな KPI を計算することもできます。
- [脆弱性とセキュリティで保護された構成の評価をエクスポートする](get-assessment-methods-properties.md) Api <br> Defender 脆弱性管理データをデバイスごとにプルする API のコレクションを追加します。 セキュリティで保護された構成評価、ソフトウェア インベントリの評価、ソフトウェアの脆弱性の評価など、さまざまな種類のデータを取得するための API 呼び出しが異なります。 各 API 呼び出しには、組織内のデバイスに必要なデータが含まれています。
- [修復アクティビティ](get-remediation-methods-properties.md) Api <br> テナントに作成された Defender 脆弱性管理修復アクティビティを含む応答を含む API のコレクションを追加します。 応答情報の種類には、ID 別の 1 つの修復アクティビティ、すべての修復アクティビティ、および 1 つの修復アクティビティの公開デバイスが含まれます。
- [デバイス検出](device-discovery.md) <br> 余分なアプライアンスや煩雑なプロセス変更を必要とせずに、会社のネットワークに接続されているアンマネージド デバイスを見つけるのに役立ちます。 オンボードされたデバイスを使用すると、ネットワーク内の管理されていないデバイスを見つけて、脆弱性とリスクを評価できます。 その後、検出されたデバイスをオンボードして、ネットワーク内にアンマネージド エンドポイントを持つことに関連するリスクを軽減できます。

   > [!IMPORTANT]
   > Standard Discovery は、2021 年 7 月 19 日からのすべてのお客様の既定のモードになります。 [設定] ページで、基本モードを保持することを選択できます。

- [デバイス グループ定義に、](/microsoft-365/security/defender-endpoint/machine-groups) 条件ごとに複数の値を含めることができるようになりました。 複数のタグ、デバイス名、ドメインを 1 つのデバイス グループの定義に設定できます。
- [モバイル アプリケーション管理のサポート](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/announcing-new-capabilities-on-android-and-ios/ba-p/2442730) <br> この機能強化により、Intuneがモバイル アプリケーションの管理に使用されている場合に、マネージド アプリケーション内で組織のデータを保護Microsoft Defender for Endpointできます。 モバイル アプリケーション管理の詳細については、 [このドキュメントを参照してください](/mem/intune/apps/mam-faq)。
- [Microsoft Tunnel VPN の統合](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/announcing-new-capabilities-on-android-and-ios/ba-p/2442730) <br> Microsoft Tunnel VPN 機能は、Android 用のMicrosoft Defender for Endpoint アプリと統合されるようになりました。 この統合により、組織は 1 つのセキュリティ アプリでシンプルなエンド ユーザー エクスペリエンスを提供できます。モバイル脅威防御とモバイル デバイスからオンプレミスリソースにアクセスする機能の両方を提供し、セキュリティチームと IT チームは、使い慣れたのと同じ管理者エクスペリエンスを維持できます。
- [iOS での脱獄検出](/microsoft-365/security/defender-endpoint/ios-configure-features#conditional-access-with-defender-for-endpoint-on-ios) <br> iOS でのMicrosoft Defender for Endpointでの脱獄検出機能が一般公開されました。 これにより、既に存在するフィッシング保護が追加されます。  詳細については、「 [デバイス リスク信号に基づいて条件付きアクセス ポリシーを設定する](/microsoft-365/security/defender-endpoint/ios-configure-features)」を参照してください。


## <a name="march-2021"></a>2021 年 3 月
- [Microsoft 365 Defender ポータルを使用して組織の改ざん防止を管理する](manage-tamper-protection-microsoft-365-defender.md) <br> *テナントアタッチ* と呼ばれる方法を使用して、Windows 10、Windows Server 2016、Windows Server 2019、Windows Server 2022 の改ざん防止設定を管理できます。


## <a name="january-2021"></a>2021 年 1 月

- [Azure 仮想デスクトップ](https://azure.microsoft.com/services/virtual-desktop/) <br> Microsoft Defender for Endpoint Azure Virtual Desktop のサポートが追加されました。
