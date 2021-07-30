---
title: Microsoft Defender for Endpoint の新機能
description: Microsoft Defender for Endpoint の最新リリースで一般的に利用可能な機能 (GA) と、Windows 10 および Windows サーバーのセキュリティ機能を参照してください。
keywords: Microsoft Defender for Endpoint の新機能、ga、一般提供、機能、利用可能、新しい
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: secure
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 33bd21cb338d5c792e6241ac61f75712ecc1ad45
ms.sourcegitcommit: d817a3aecb700f7227a05cd165ffa7dbad67b09d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/29/2021
ms.locfileid: "53656069"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpoint の新機能

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を体験してみませんか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-pullalerts-abovefoldlink)

Microsoft Defender for Endpoint の最新リリースでは、次の機能 (GA) と、Windows 10 および Windows Server のセキュリティ機能が提供されています。

プレビュー機能の詳細については、「プレビュー機能」 [を参照してください](preview.md)。


> [!TIP]
> RSS フィード: 次の URL をコピーしてフィード リーダーに貼り付け、このページが更新された場合に通知を受け取ります。
>
> ```https
> /api/search/rss?search=%22features+are+generally+available+%28GA%29+in+the+latest+release+of+Microsoft+Defender+for+Endpoint%22&locale=en-us&facet=
> ```

## <a name="june-2021"></a>2021 年 6 月

- [デルタ エクスポート ソフトウェアの脆弱性評価](get-assessment-methods-properties.md#31-methods) API <br> 脆弱性とセキュリティで保護された構成 API コレクションのエクスポート [評価に](get-assessment-methods-properties.md) 加えて。 <br> デバイス別に組織のソフトウェア脆弱性評価のスナップショット全体を取得するために使用される完全なソフトウェア脆弱性評価 (JSON 応答) とは異なり、デルタ エクスポート API 呼び出しは、選択した日付と現在の日付 ("デルタ" API 呼び出し) の間に発生した変更のみを取得するために使用されます。 毎回大量のデータを含む完全なエクスポートを取得する代わりに、新規、固定、および更新された脆弱性に関する特定の情報のみを取得します。 デルタ エクスポート API 呼び出しを使用して、「修正された脆弱性の数」や「組織に追加された新しい脆弱性の数」など、さまざまな KPI を計算することもできます。

- [脆弱性とセキュリティで保護された構成の評価をエクスポートする](get-assessment-methods-properties.md) API <br> デバイス単位でデータを取得脅威と脆弱性の管理 API のコレクションを追加します。 さまざまな種類のデータを取得するためのさまざまな API 呼び出しがあります。セキュリティで保護された構成評価、ソフトウェア インベントリ評価、およびソフトウェアの脆弱性評価。 各 API 呼び出しには、組織内のデバイスに必要なデータが含まれる。

- [修復アクティビティ](get-remediation-methods-properties.md) API <br>  テナントで作成された修復アクティビティを脅威と脆弱性の管理応答を含む API のコレクションを追加します。 応答情報の種類には、ID による 1 つの修復アクティビティ、すべての修復アクティビティ、および 1 つの修復アクティビティの公開されたデバイスが含まれます。

- [デバイス検出](device-discovery.md) <br> 追加のアプライアンスや面倒なプロセス変更を必要とせずに、企業ネットワークに接続されている管理されていないデバイスを見つけるのに役立ちます。 オンボード デバイスを使用すると、ネットワーク内の管理されていないデバイスを見つけて、脆弱性とリスクを評価できます。 その後、検出されたデバイスをオンボードして、ネットワークに管理されていないエンドポイントを持つことに関連するリスクを軽減できます。

   > [!IMPORTANT]
   > 標準検出は、2021 年 7 月 19 日からすべてのユーザーの既定のモードになります。 基本モードは、[設定] ページで保持できます。

- [デバイス グループ定義には、](/microsoft-365/security/defender-endpoint/machine-groups) 条件ごとに複数の値を含めることができます。 複数のタグ、デバイス名、ドメインを 1 つのデバイス グループの定義に設定できます。

## <a name="march-2021"></a>2021 年 3 月
- [アプリケーションを使用して改ざん防止を管理Microsoft Defender セキュリティ センター](prevent-changes-to-security-settings-with-tamper-protection.md#manage-tamper-protection-for-your-organization-using-the-microsoft-365-defender-portal) <br> テナント接続というメソッドを使用して、Windows 10、Windows Server 2016、Windows サーバー 2019 の改ざん防止設定 *を管理できます*。


## <a name="january-2021"></a>2021 年 1 月

- [Windows Virtual Desktop](https://azure.microsoft.com/services/virtual-desktop/) <br> Microsoft Defender for Endpoint では、仮想デスクトップのサポートWindows追加しました。

## <a name="december-2020"></a>2020 年 12 月

- [iOS 用 Microsoft Defender for Endpoint API](microsoft-defender-endpoint-ios.md) <br> Microsoft Defender for Endpoint が iOS のサポートを追加しました。 iOS で Microsoft Defender for Endpoint をインストール、構成、更新、および使用する方法について説明します。

## <a name="september-2020"></a>2020 年 9 月

- [Android 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-android.md) <br> Microsoft Defender for Endpoint が Android のサポートを追加しました。 Android 上で Microsoft Defender for Endpoint をインストール、構成、更新、および使用する方法について説明します。
- [macOS の脆弱性の管理とセキュリティ](tvm-supported-os.md)<br> macOS 脆弱性の管理脅威と脅威はパブリック プレビューに表示され、macOS デバイスの脆弱性を継続的に検出し、リスクに焦点を当て、修復の優先順位を設定するのに役立ちます。 詳細については、[この Microsoft Tech のブログCommunityを参照してください](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/microsoft-defender-for-endpoint-adds-depth-and-breadth-to-threat/ba-p/1695824)。

## <a name="august-2020"></a>2020 年 8 月

- [Android 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-android.md) <br> Microsoft Defender for Endpoint が Android のサポートを追加しました。 Android で Microsoft Defender for Endpoint をインストール、構成、および使用する方法について説明します。

## <a name="july-2020"></a>2020 年 7 月

- [証明書のインジケーターを作成 ](manage-indicators.md) <br> 証明書を許可またはブロックするインジケーターを作成します。

## <a name="june-2020"></a>2020 年 6 月

- [Linux 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-linux.md) <br> Microsoft Defender for Endpoint が Linux のサポートを追加しました。 Linux で Microsoft Defender for Endpoint をインストール、構成、更新、および使用する方法について説明します。

- [評価ラボの攻撃シミュレーター](evaluation-lab.md#threat-simulator-scenarios) <br> Microsoft Defender for Endpoint は、さまざまな脅威シミュレーション プラットフォームと提携し、ポータル内からプラットフォームの機能を簡単にテストできます。

## <a name="april-2020"></a>2020 年 4 月

- [脅威&管理 API のサポート](exposed-apis-list.md) <BR>脅威&脆弱性管理関連の API 呼び出し (組織の脅威暴露スコアまたはデバイスのセキュリティで保護されたスコアを取得する、ソフトウェアとデバイスの脆弱性インベントリ、ソフトウェアバージョンの配布、デバイスの脆弱性情報、セキュリティの推奨事項情報を取得する)を実行します。 詳細については、[この Microsoft Tech のブログCommunityを参照してください](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/threat-amp-vulnerability-management-apis-are-now-generally/ba-p/1304615)。

## <a name="november-december-2019"></a>November-December 2019

- [macOS 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md) <BR> Microsoft Defender for Endpoint on macOS では、次世代の保護を Mac デバイスに提供します。 統合エンドポイント セキュリティ プラットフォームのコア コンポーネントは、エンドポイントの検出と応答を含む Mac デバイス [で使用できます](microsoft-defender-endpoint-mac.md)。

- [脅威&脆弱性管理アプリケーションとアプリケーション バージョンの終末情報](tvm-security-recommendation.md) <BR>使用期限に達したアプリケーションとアプリケーションのバージョンはタグ付けまたはラベル付けされ、サポートされなくなったことを認識し、アンインストールまたは置換を行うアクションを実行できます。 これにより、パッチが適用されていないアプリケーションによるさまざまな脆弱性の暴露に関連するリスクが軽減されます。

- [脅威&脆弱性管理高度なハンティング スキーマ](advanced-hunting-schema-reference.md) <BR>高度な&の脅威管理テーブルを使用して、ソフトウェア インベントリ、脆弱性ナレッジベース、セキュリティ構成評価、およびセキュリティ構成ナレッジベースに関するクエリを実行します。

 - [脅威&の管理の役割ベースのアクセス制御](user-roles.md#create-roles-and-assign-the-role-to-an-azure-active-directory-group) <BR>新しいアクセス許可を使用して、SecOps 指向の役割、Threat & の脆弱性管理指向の役割、またはハイブリッド ロールを最大限に柔軟に作成し、承認されたユーザーのみが特定のデータにアクセスしてタスクを実行できます。 また、Threat & の脆弱性管理の役割が脆弱性に関連するデータのみを表示できるかどうか、または修復と例外を作成および管理できるかどうかを指定することで、さらに細分化できます。

- [デバイスの正常性とコンプライアンスのレポート](machine-reports.md) <br/> デバイスの正常性とコンプライアンス レポートは、組織内のデバイスに関する高レベルの情報を提供します。

## <a name="october-2019"></a>2019 年 10 月

- [IP アドレス、URL、ドメインのインジケーター](manage-indicators.md) <BR> 独自の脅威インテリジェンスを使用して URL/ドメインを許可またはブロックできます。

- [Microsoft 脅威エキスパート - エキスパート オンデマンド](microsoft-threat-experts.md) <BR> これで、調査のコンテキストで役立Microsoft 脅威エキスパート、ポータル内のいくつかの場所からユーザーに問い合うオプションが追加されました。

- [接続された Azure AD アプリケーション](connected-applications.md)<br> [接続されたアプリケーション] ページには、組織内の Microsoft Defender for Endpoint に接続AD Azure アプリケーションに関する情報が表示されます。

- [API エクスプローラー](api-explorer.md)<br> API エクスプローラーを使用すると、API クエリの作成と実行、使用可能な Microsoft Defender for Endpoint API エンドポイントの要求のテストと送信が容易になります。

## <a name="september-2019"></a>2019 年 9 月

- [Intune を使用したタンパープロテクションの設定](prevent-changes-to-security-settings-with-tamper-protection.md) <br/> デバイス管理ポータル (Intune) で、組織のタンパープロテクションをオン (またはオフ) Microsoft 365有効にできます。

- [ライブ応答](live-response.md) <BR> リモート シェル接続を使用してデバイスに瞬時にアクセスします。 詳細な調査作業を行い、迅速に特定された脅威 (リアルタイム) を含む即時対応アクションを実行します。

- [評価ラボ](evaluation-lab.md) <BR> Microsoft Defender for Endpoint 評価ラボは、プラットフォームの機能の評価、シミュレーションの実行、予防、検出、修復機能の実行に集中できるよう、デバイスと環境構成の複雑さを排除するように設計されています。

- [Windows Server 2008 R2 SP1](configure-server-endpoints.md) <BR> これで、サーバー 2008 R2 SP1 Windowsオンボードできます。

## <a name="june-2019"></a>2019 年 6 月

- [脅威&の管理](next-gen-threat-and-vuln-mgt.md) <BR> エンドポイントの脆弱性と誤った構成の検出、事前設定、修復にリスクベースのアプローチを使用する新しい組み込み機能。

- [デバイスの正常性とコンプライアンス レポート](machine-reports.md)  デバイスの正常性とコンプライアンス レポートは、組織内のデバイスに関する高レベルの情報を提供します。

## <a name="may-2019"></a>2019 年 5 月

- [脅威に対する保護のレポート](threat-protection-reports.md)<BR>脅威保護レポートは、組織で生成されたアラートに関する高レベルの情報を提供します。

- [Microsoft 脅威エキスパート](microsoft-threat-experts.md)<BR> Microsoft 脅威エキスパートは、Microsoft Defender for Endpoint の新しい管理された脅威検出サービスで、予防的な狩猟、事前設定、追加のコンテキストと分析情報を提供し、セキュリティ 運用センター (SOC) が脅威を迅速かつ正確に特定して対応する権限をさらに強化します。 Microsoft のお客様がセキュリティ運用機能を強化するために利用できる専門知識と光学の層が追加Microsoft 365。

- [インジケーター](ti-indicator.md) <BR> インジケーターの API が一般提供されています。

- [相互運用性](partner-applications.md) <BR> Microsoft Defender for Endpoint は、プラットフォームの検出、調査、および脅威インテリジェンス機能の強化に役立つサード パーティ製アプリケーションをサポートしています。

## <a name="april-2019"></a>2019 年 4 月

- [Microsoft 脅威エキスパートターゲット攻撃通知機能](microsoft-threat-experts.md) <BR> Microsoft 脅威エキスパートの標的型攻撃通知アラートは、組織に合わせて調整され、迅速に配信できる限り多くの情報を提供するため、タイムライン、侵害の範囲、侵入方法など、ネットワーク内の重大な脅威に注意を払います。

- [Microsoft Defender for Endpoint API](apis-intro.md) <BR> Microsoft Defender for Endpoint は、一連のプログラム API を通じて、そのデータとアクションの多くを公開します。 これらの API を使用すると、Microsoft Defender for Endpoint の機能に基づいてワークフローを自動化し、革新することができます。

## <a name="february-2019"></a>2019 年 2 月

- [インシデント](view-incidents-queue.md) <BR> インシデントは、Microsoft Defender for Endpoint の新しいエンティティであり、関連するすべてのアラートと関連エンティティをまとめ、より広範な攻撃ストーリーをナレーションし、アナリストが複雑な脅威の観点をよりよく理解します。

- [以前のバージョンの Windows をオンボードする](onboard-downlevel.md)<BR> Microsoft Defender for Endpoint センサー Windowsセンサー データを送信できるよう、オンボードでサポートされているバージョンのデバイスを使用します。

## <a name="october-2018"></a>2018 年 10 月

- [攻撃面の減少ルール](attack-surface-reduction.md)<BR>すべての攻撃表面の縮小ルールは、サーバー 2019 Windowsサポートされています。

- [制御されたフォルダー アクセス](enable-controlled-folders.md)<BR> フォルダー アクセスの制御が、サーバー 2019 Windowsサポートされています。

- [カスタム検出](manage-indicators.md)<BR>カスタム検出を使用すると、カスタム クエリを作成して、疑わしい脅威や新しい脅威などの任意の種類の動作についてイベントを監視できます。 これは、カスタム検出ルールの作成を通じて高度な狩猟の力を活用することで実行できます。

- [Azure Defender との統合](configure-server-endpoints.md)<BR> Microsoft Defender for Endpoint は Azure Defender と統合して、包括的なサーバー保護ソリューションを提供します。 この統合により、Azure Defender は Microsoft Defender for Endpoint の機能を活用して、サーバーの脅威検出を強化Windowsできます。

- [マネージド セキュリティ サービス プロバイダー (MSSP) のサポート](mssp-support.md)<BR> Microsoft Defender for Endpoint は、MSSP 統合を提供することで、このシナリオのサポートを追加します。 この統合により、MSSP は MSSP のお客様の Microsoft Defender セキュリティ センター ポータルへのアクセス、電子メール通知のフェッチ、セキュリティ情報とイベント管理 (SIEM) ツールを使用してアラートをフェッチする、というアクションを実行できます。

- [リムーバブル デバイスコントロール](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/19/windows-defender-atp-has-protections-for-usb-and-removable-devices/)<BR>Microsoft Defender for Endpoint には、特定のハードウェアの ID を許可またはブロックするための新しい設定を含む、リムーバブル デバイスからの脅威を防止するための複数の監視および制御機能が提供されています。

- [iOS デバイスと Android デバイスのサポート](configure-endpoints-non-windows.md)<BR> iOS デバイスと Android デバイスがサポートされ、サービスにオンボードできます。

- [脅威の分析](threat-analytics.md)<BR>
Threat Analytics は、新たな脅威やアウトブレイクが特定されるとすぐに Microsoft Defender for Endpoint リサーチ チームが発行する一連の対話型レポートです。 このレポートは、セキュリティ運用チームが環境への影響を評価し、組織の回復力を高め、特定の脅威を防ぐための推奨アクションを提供するのに役立ちます。

- 新しいWindows 10バージョン 1809 では、次の 2 つの新しい攻撃表面縮小ルールがあります。
  - Adobe Reader の子プロセスの作成をブロックする
  - 通信アプリケーションOffice子プロセスの作成をブロックします。

- [Microsoft Defender ウイルス対策](microsoft-defender-antivirus-in-windows-10.md)
  - マルウェア対策スキャン インターフェイス (AMSI) は、VBA マクロOfficeに拡張されました。 [Office VBA + AMSI: 悪意のあるマクロにベールを分けます](https://cloudblogs.microsoft.com/microsoftsecure/2018/09/12/office-vba-amsi-parting-the-veil-on-malicious-macros/)。
  - Microsoft Defender ウイルス対策バージョン 1809 Windows 10の新機能で、サンドボックス[(プレビュー](https://www.microsoft.com/security/blog/2018/10/26/windows-defender-antivirus-can-now-run-in-a-sandbox) ) 内で実行し、セキュリティを強化しました。
  - [スキャンの CPU 優先度設定](configure-advanced-scan-types-microsoft-defender-antivirus.md)をMicrosoft Defender ウイルス対策します。

## <a name="march-2018"></a>2018 年 3 月

- [高度な追求](advanced-hunting-overview.md)

   Microsoft Defender for Endpoint の高度な検索を使用してデータをクエリします。

- [攻撃面の減少ルール](/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard)

  新しい攻撃表面の縮小ルール:

  - ランサムウェアに対する高度な保護の使用
  - ローカル セキュリティ機関サブシステムからの資格情報のWindowsをブロックする (lsass.exe)
  - PSExec および WMI コマンドから発生するプロセス作成をブロックする
  - USB から実行される信頼されていないプロセスと署名されていないプロセスをブロックする
  - メール クライアントと Web メールから実行可能なコンテンツをブロックする

- [調査と修復の自動化](automated-investigations.md)<BR> 自動調査を使用して、脅威を調査および修復します。

    > [!NOTE]
    > バージョン 1803 Windows 10以降のバージョンから使用できます。

- [条件付きアクセス](conditional-access.md) <br> 条件付きアクセスを有効にして、ユーザー、デバイス、およびデータをより良く保護します。

- [Microsoft Defender for Endpoint Community センター](community.md)<BR>
    Microsoft Defender for Endpoint Community センターは、コミュニティ メンバーが製品に関するエクスペリエンスを学び、共同作業し、共有できる場所です。

- [制御されたフォルダー アクセス](enable-controlled-folders.md)<BR>
フォルダー アクセスの制御を使用して、信頼されていないプロセスがディスク セクターに書き込むのをブロックできます。

- [Windows 以外のデバイスをオンボードする](configure-endpoints-non-windows.md)<BR>
    Microsoft Defender for Endpoint は、セキュリティ プラットフォームだけでなく、Windowsプラットフォームにも一元的なセキュリティWindows提供します。 サポートされているさまざまなオペレーティング システム (OS) からのアラートを、組織のネットワークMicrosoft Defender セキュリティ センター保護することができます。

- [役割ベースのアクセス制御 (RBAC)](rbac.md)<BR>
    役割ベースのアクセス制御 (RBAC) を使用して、セキュリティ運用チーム内に役割とグループを作成して、ポータルへの適切なアクセスを許可できます。


- [Microsoft Defender ウイルス対策](microsoft-defender-antivirus-in-windows-10.md)<BR>
Microsoft Defender ウイルス対策サービス間で検出状態を共有Microsoft 365 Microsoft Defender for Endpoint との相互運用が可能になります。 詳細については、「クラウドで提供される保護を通じて、Microsoft Defender ウイルス対策[に次世代テクノロジを使用する」を参照してください](cloud-protection-microsoft-defender-antivirus.md)。

    一目でブロックすると、移植できない実行可能ファイル (JS、VBS、マクロなど) と実行可能ファイルをブロックできます。 詳細については、「一目で [ブロックを有効にする」を参照してください](configure-block-at-first-sight-microsoft-defender-antivirus.md)。
