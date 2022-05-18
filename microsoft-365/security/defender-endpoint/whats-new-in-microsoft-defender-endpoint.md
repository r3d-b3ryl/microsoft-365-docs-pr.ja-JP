---
title: Microsoft Defender for Endpoint の新機能
description: Microsoft Defender for Endpointの最新リリースで一般公開されている機能 (GA) と、Windows 10およびWindows サーバーのセキュリティ機能を確認します。
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
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 615a68d7725e180e512674909f490e27d3da6771
ms.sourcegitcommit: da6b3cb3b2ccfcdcd5091efce8290b6c486547db
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/18/2022
ms.locfileid: "65468802"
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

- [Defender for Endpoint on macOSの新機能](mac-whatsnew.md)
- [Defender for Endpoint on iOSの新機能](ios-whatsnew.md)
- [Defender for Endpoint on Linux の新機能](linux-whatsnew.md)

## <a name="may-2022"></a>2022 年 5 月
- [macOSの改ざん防止 (プレビュー)](tamperprotection-macos.md)<br>改ざん防止は、macOSでのMicrosoft Defender for Endpointの不正な削除を防ぐのに役立ちます。


## <a name="april-2022"></a>2022 年 4 月
- [Windows Server 2012 R2 とWindows Server 2016) のオンボードと機能パリティを更新しました](configure-server-endpoints.md)<br/> 新しい統合ソリューション パッケージが一般公開され、依存関係とインストール手順を削除することで、サーバーのオンボードが容易になりました。 さらに、この統合ソリューション パッケージには、多くの新機能が追加されています。
- Tunnelとの統合。 iOSのMicrosoft Defender for Endpointは、1 つのアプリでセキュリティと接続を有効にする VPN ゲートウェイ ソリューションである Microsoft Tunnel と統合できるようになりました。この機能は、以前はAndroidでのみ使用できます。 [詳細情報](https://techcommunity.microsoft.com/t5/microsoft-endpoint-manager-blog/what-s-new-in-microsoft-endpoint-manager-2204-april-edition/ba-p/3297995)

## <a name="january-2022"></a>2022 年 1 月

- 評価ラボの機能強化: Windows 11デバイスと Linux デバイスをラボに追加できるようになりました。 

- AndroidとiOSの脅威と脆弱性の管理が一般公開されるようになりました。 [詳細情報](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/announcing-general-availability-of-vulnerability-management/ba-p/3071663) を参照してください。

## <a name="december-2021"></a>2021 年 12 月

- 脅威と脆弱性の管理は、アプリケーションとコンポーネントの Log4j の脆弱性を特定するのに役立ちます。 [詳細情報](https://www.microsoft.com/security/blog/2021/12/11/guidance-for-preventing-detecting-and-hunting-for-cve-2021-44228-log4j-2-exploitation/#TVM) を参照してください。

- IoT デバイスの検出 (プレビュー): [デバイス検出](device-discovery.md) は、企業ネットワークに接続されているアンマネージド IoT デバイスを見つけるのに役立つようになりました。 これにより、他の IT デバイス (ワークステーション、サーバー、モバイル) と共に IoT インベントリを 1 つの統合ビューで表示できます。

- [Microsoft Defender for IoT 統合 (プレビュー)](enable-microsoft-defender-for-iot-integration.md): この統合により、Microsoft Defender for IoT によって提供されるエージェントレス監視機能を使用して、デバイス検出機能が強化されます。 これにより、ネットワーク内の IoT デバイスの特定、識別、セキュリティ保護に役立つ可視性が向上します。

## <a name="november-2021"></a>2021 年 11 月

- [セキュリティ構成管理](security-config-management.md) <br/> Microsoft IntuneまたはMicrosoft Endpoint Configuration ManagerのMicrosoft エンドポイント マネージャーによって管理されていないデバイスが Microsoft Defender のセキュリティ構成を直接受信する機能。エンドポイント マネージャー。

- クロスプラットフォームサポートの機能強化。

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

- [Delta Export ソフトウェアの脆弱性評価](get-assessment-methods-properties.md#31-methods) API <br> [脆弱性とセキュリティで保護された構成 API コレクションのエクスポート評価に](get-assessment-methods-properties.md)加えて。 <br> 完全なソフトウェア脆弱性評価 (JSON 応答) とは異なり、これは、デバイス別に組織のソフトウェア脆弱性評価のスナップショット全体を取得するために使用されます。差分エクスポート API 呼び出しは、選択した日付と現在の日付 ("delta" API 呼び出し) の間に発生した変更のみをフェッチするために使用されます。 毎回大量のデータを含む完全なエクスポートを取得する代わりに、新しい脆弱性、修正された脆弱性、更新された脆弱性に関する特定の情報のみを取得します。 Delta export API 呼び出しを使用して、「修正された脆弱性の数」や「組織に追加された新しい脆弱性の数」など、さまざまな KPI を計算することもできます。

- [脆弱性とセキュリティで保護された構成の評価をエクスポートする](get-assessment-methods-properties.md) API <br> デバイスごとにデータをプル脅威と脆弱性の管理 API のコレクションを追加します。 セキュリティで保護された構成評価、ソフトウェア インベントリの評価、ソフトウェアの脆弱性の評価など、さまざまな種類のデータを取得するための API 呼び出しが異なります。 各 API 呼び出しには、組織内のデバイスに必要なデータが含まれています。

- [修復アクティビティ](get-remediation-methods-properties.md) API <br> テナントに作成された脅威と脆弱性の管理修復アクティビティを含む応答を含む API のコレクションを追加します。 応答情報の種類には、ID 別の 1 つの修復アクティビティ、すべての修復アクティビティ、および 1 つの修復アクティビティの公開デバイスが含まれます。

- [デバイス検出](device-discovery.md) <br> 余分なアプライアンスや煩雑なプロセス変更を必要とせずに、会社のネットワークに接続されているアンマネージド デバイスを見つけるのに役立ちます。 オンボードされたデバイスを使用すると、ネットワーク内の管理されていないデバイスを見つけて、脆弱性とリスクを評価できます。 その後、検出されたデバイスをオンボードして、ネットワーク内にアンマネージド エンドポイントを持つことに関連するリスクを軽減できます。

   > [!IMPORTANT]
   > Standard Discovery は、2021 年 7 月 19 日からのすべてのお客様の既定のモードになります。 [設定] ページで、基本モードを保持することを選択できます。

- [デバイス グループ定義に、](/microsoft-365/security/defender-endpoint/machine-groups) 条件ごとに複数の値を含めることができるようになりました。 複数のタグ、デバイス名、ドメインを 1 つのデバイス グループの定義に設定できます。

- [モバイル アプリケーション管理のサポート](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/announcing-new-capabilities-on-android-and-ios/ba-p/2442730) <br> この機能強化により、Intuneがモバイル アプリケーションの管理に使用されている場合に、マネージド アプリケーション内で組織のデータを保護Microsoft Defender for Endpointできます。 モバイル アプリケーション管理の詳細については、 [このドキュメントを参照してください](/mem/intune/apps/mam-faq)。

- [Microsoft Tunnel VPN 統合](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/announcing-new-capabilities-on-android-and-ios/ba-p/2442730) <br> Microsoft Tunnel VPN 機能は、Android用のMicrosoft Defender for Endpoint アプリと統合されるようになりました。 この統合により、組織は 1 つのセキュリティ アプリでシンプルなエンド ユーザー エクスペリエンスを提供できます。モバイル脅威の防御とモバイル デバイスからオンプレミスのリソースにアクセスする機能の両方を提供し、セキュリティチームと IT チームは、使い慣れた管理者エクスペリエンスを維持できます。

- [iOSでの脱獄検出](/microsoft-365/security/defender-endpoint/ios-configure-features#conditional-access-with-defender-for-endpoint-on-ios) <br> iOSのMicrosoft Defender for Endpointでの脱獄検出機能が一般公開されました。 これにより、既に存在するフィッシング保護が追加されます。  詳細については、「 [デバイス リスク信号に基づいて条件付きアクセス ポリシーを設定する](/microsoft-365/security/defender-endpoint/ios-configure-features)」を参照してください。


## <a name="march-2021"></a>2021 年 3 月
- [Microsoft 365 Defender ポータルを使用して改ざん防止を管理する](prevent-changes-to-security-settings-with-tamper-protection.md#manage-tamper-protection-for-your-organization-using-the-microsoft-365-defender-portal) <br> *テナントアタッチ* と呼ばれるメソッドを使用して、Windows 10、Windows Server 2016、Windows Server 2019、Windows Server 2022 で改ざん防止設定を管理できます。


## <a name="january-2021"></a>2021 年 1 月

- [Azure 仮想デスクトップ](https://azure.microsoft.com/services/virtual-desktop/) <br> Microsoft Defender for Endpoint Azure Virtual Desktop のサポートが追加されました。
