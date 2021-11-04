---
title: Microsoft 365 エンドポイント データ損失防止を開始する
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
ms.localizationpriority: high
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: Microsoft 365 エンドポイントのデータ損失防止を設定して、ファイルアクティビティを監視し、それらのファイルの保護アクションをエンドポイントに実装します。
ms.openlocfilehash: 22f7e2eb1476543eb1aed9d772333f3ae7843477
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2021
ms.locfileid: "60703727"
---
# <a name="get-started-with-endpoint-data-loss-prevention"></a>エンドポイント データ損失防止を開始する

Microsoft Endpoint Data Loss Prevention (Endpoint DLP) は、Microsoft 365 サービス全体で機密アイテムを検出して保護する Microsoft 365 Data Loss Prevention (DLP) スイートの機能の一部です。 MicrosoftのすべてのDLP製品の詳細については、「[データ損失防止の概要](dlp-learn-about-dlp.md)」を参照してください。 エンドポイント DLP の詳細については、「[エンドポイント データ損失防止の説明](endpoint-dlp-learn-about.md)」を参照してください。

Microsoft Endpoint DLP を使用すると、Catalina 10.15 以上を実行する Windows 10 デバイスと macOS デバイス *(プレビュー)* を監視できます。 デバイスがオンボードされると、DLP は機密性の高いアイテムが使用および共有されたことを検出します。 これにより、適切に使用および保護されていることを確認し、危険にさらされる可能性のある動作を防止するために必要な可視性と制御を得ることができます。

## <a name="before-you-begin"></a>はじめに

### <a name="skusubscriptions-licensing"></a>SKU /サブスクリプションライセンス

Endpoint DLP を開始する前に、「[Microsoft 365サブスクリプション](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)」とアドオンを確認しなければなりません。 Endpoint DLP 機能にアクセスして使用するには、次のいずれかのサブスクリプションまたはアドオンが必要です。

- Microsoft 365 E5
- Microsoft 365 A5 (EDU) 
- Microsoft 365 E5 コンプライアンス
- Microsoft 365 A5 コンプライアンス
- Microsoft 365 E5 の情報保護とガバナンス
- Microsoft 365 A5 の情報保護とガバナンス

### <a name="permissions"></a>許可

デバイス管理を有効にするには、使用するアカウントが次のいずれかの役割のメンバーでなければなりません。

- グローバル管理者
- セキュリティ管理者
- コンプライアンス管理者

カスタムアカウントを使用してデバイス管理設定を表示する場合は、次のいずれかの役割でなければなりません。

- グローバル管理者
- コンプライアンス管理者
- コンプライアンスデータ管理者
- グローバルリーダー

カスタムアカウントを使用してオンボーディング/オフボーディングページにアクセスする場合は、次のいずれかの役割でなければなりません。

- グローバル管理者
- コンプライアンス管理者

カスタムアカウントを使用してデバイスの監視をオン/オフにする場合は、次のいずれかの役割でなければなりません。

- グローバル管理者
- コンプライアンス管理者

Endpoint DLP からのデータは、[Activity エクスプローラー](data-classification-activity-explorer.md)で表示します。 Activity エクスプローラーに権限を付与する役割は4つあります。データへのアクセスに使用するアカウントは、次のいずれかのメンバーでなければなりません。

- グローバル管理者
- コンプライアンス管理者
- セキュリティ管理者
- コンプライアンスデータ管理者

### <a name="prepare-your-windows-10-endpoints"></a>Windows 10 エンドポイントを準備する

これらの要件を満たすために、Endpoint DLP の導入を計画している Windows 10 デバイスを確認してください。

1. Windows 10 x64 ビルド 1809 以降を実行している必要があります。

1. マルウェア対策クライアントのバージョンは 4.18.2009.7 以降です。 Windows セキュリティ アプリを開いて現在のバージョンを確認し、[設定] アイコンを選択して、[バージョン情報] を選択します。 バージョン番号は、マルウェア対策クライアントのバージョンの下に表示されます。 Windows Update KB4052623 をインストールして、最新のマルウェア対策クライアントのバージョンに更新します。

   > [!NOTE]
   > 注: Windows セキュリティ コンポーネントはいずれもアクティブである必要はなく、Windows セキュリティの状態に関係なくエンドポイント DLP を実行できますが、[リアルタイム保護と動作の監視](/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus)) を有効にする必要があります。

1. 次の Windows Update がインストールされています。

   > [!NOTE]
   > これらの更新プログラムは、デバイスをエンドポイント DLP にオンボードするための前提条件ではありませんが、重要な問題の修正が含まれているため、製品を使用する前にインストールする必要があります。

   - Windows 10 1809 の場合 - KB4559003、KB4577069、KB4580390
   - Windows 10 1903 または 1909 の場合 - KB4559004、KB4577062、KB4580386
   - Windows 10 2004 の場合 - KB4568831、KB4577063
   - Office 2016 を実行しているデバイスの場合 (他の Office バージョンではない) - KB4577063

1. すべてのデバイスは、次のいずれかを満たしている必要があります。

   - [Azure Active Directory (Azure AD) への参加](/azure/active-directory/devices/concept-azure-ad-join)
   - [Hybrid Azure AD への参加](/azure/active-directory/devices/concept-azure-ad-join-hybrid)
   - [AAD の登録](/azure/active-directory/user-help/user-help-register-device-on-network)

1. エンドポイント デバイスに Microsoft Chromium Edge ブラウザーをインストールして、クラウドへのアップロード アクティビティのポリシー アクションを適用します。 「[Chromium ベースの新しい Microsoft Edge をダウンロードする](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)」を参照してください。 デバイスで Chrome ブラウザーを使用している場合は、[Microsoft Compliance Extension](dlp-chrome-learn-about.md#learn-about-the-microsoft-compliance-extension) をインストールし、クラウド アクティビティへのアップロードに対してポリシー アクションを適用できます。

1. Microsoft 365 アプリ バージョン 2004 - 2008 の月次エンタープライズ チャネルを使用している場合、Office コンテンツを分類する Endpoint DLP に既知の問題があり、バージョン 2009 以降に更新する必要があります。 現在のバージョンについては「[Microsoft 365 アプリの更新履歴 (日付別の一覧)](/officeupdates/update-history-microsoft365-apps-by-date)」をご覧ください。 この問題の詳細については、[2020 年の最新のチャネル リリースのリリース ノート](/officeupdates/current-channel#version-2010-october-27)の「Office スイート」セクションを参照してください。

1. デバイス プロキシを使用してインターネットに接続するエンドポイントがある場合は、「[エンドポイント DLP のデバイス プロキシとインターネット接続設定の構成](endpoint-dlp-configure-proxy.md)」の手順に従います。

## <a name="prepare-your-macos-devices-preview"></a>macOS デバイスを準備する (プレビュー)

「[Microsoft 365 への macOS デバイスのオンボードに関する概要 (プレビュー)](device-onboarding-macos-overview.md#onboard-macos-devices-into-microsoft-365-overview-preview)」をご覧ください

## <a name="onboarding-windows-10-devices-into-device-management"></a>デバイス管理への Windows 10 デバイスのオンボーディング

デバイス上の機密アイテムを監視および保護する前に、デバイスの監視を有効にし、エンドポイントをオンボードしなければなりません。 これらのアクションはどちらも Microsoft 365 コンプライアンスポータルで行われます。

まだオンボードされていないデバイスをオンボードする場合は、適切なスクリプトをダウンロードして、それらのデバイスに展開します。「[デバイスのオンボーディング](endpoint-dlp-getting-started.md#onboarding-devices)」の手順に従ってください。

既に [Microsoft Defender for Endpoint](/windows/security/threat-protection/) にオンボーディングされているデバイスがある場合、それらは管理対象デバイスのリストに表示されます。 [「Microsoft Defender for Endpoint にオンボーディングされているデバイスを使用」の手順](?source=docs&view=o365-worldwide#with-devices-onboarded-into-microsoft-defender-for-endpoint)に従ってください。

### <a name="onboarding-devices"></a>オンボーディングデバイス

この導入シナリオでは、まだオンボーディングされていないデバイスをオンボードし、Windows 10 デバイスで意図しない共有から機密アイテムを監視および保護します。

1. [Microsoft コンプライアンスセンター](https://compliance.microsoft.com)を開きます。

2. コンプライアンスセンターの設定ページを開き、[**オンボードデバイス**]を選択します。

   > [!div class="mx-imgBorder"]
   > ![デバイス管理を有効にする。](../media/endpoint-dlp-learn-about-1-enable-device-management.png)

   > [!NOTE]
   > 通常、デバイスのオンボーディングが有効になるまで約60秒かかりますが、Microsoft サポートに連絡するまでに最大 30 分かかります。

3. [**デバイス管理**]を選択して、[**デバイス**]リストを開きます。 デバイスをオンボードするまで、リストは空になります。

4. オンボーディングプロセスを開始するには、[**オンボーディング**]を選択します。

5. これらの追加デバイスに導入する方法を[**導入方法**]リストから選択し、**パッケージをダウンロード** します。

   > [!div class="mx-imgBorder"]
   > ![導入方法。](../media/endpoint-dlp-getting-started-3-deployment-method.png)

6. 「[Windows 10 マシンのオンボーディングツールと方法](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)」の適切な手順に従います。 このリンクをクリックすると、手順 5 で選択した導入パッケージと一致する Microsoft Defender for Endpoint の手順にアクセスできるランディング ページが表示されます。

    - グループポリシーを使用した Windows 10 マシンのオンボード
    - Microsoft Endpoint Configuration Manager を使用した Windows 10 マシンのオンボード
    - モバイルデバイス管理ツールを使用した Windows 10 マシンのオンボード
    - ローカルスクリプトを使用した Windows 10 マシンのオンボード
    - シングル セッション シナリオでの非永続的な仮想デスクトップ インフラストラクチャ (VDI) マシンのオンボード

完了後、エンドポイントがオンボードされ、デバイスリストに表示され、監査アクティビティログのActivity エクスプローラーへの報告も開始されます。

> [!NOTE]
> これは、ライセンス執行時でのエクスペリエンスです。 必要なライセンスがないと、データは表示されず、アクセスできません。

### <a name="with-devices-onboarded-into-microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpoint にオンボーディングされているデバイスを使用

このシナリオでは、Microsoft Defender for Endpoint は既に導入されており、レポートするエンドポイントがあります。 これらすべてのエンドポイントが管理対象デバイスのリストに表示されます。 新しいデバイスを引き続き Endpoint DLP にオンボーディングして、[オンボーディングデバイスの手順](endpoint-dlp-getting-started.md#onboarding-devices)を使用してカバレッジを拡大します。

1. [Microsoft コンプライアンスセンター](https://compliance.microsoft.com)を開きます。

2. コンプライアンスセンターの設定ページを開き、[**デバイスの監視を有効にする**]を選択します。

3. [**デバイス管理**]を選択して、[**デバイス**]リストを開きます。 既に Microsoft Defender for Endpoint にレポートしているデバイスのリストが表示されます。

   > [!div class="mx-imgBorder"]
   > ![デバイス管理。](../media/endpoint-dlp-getting-started-2-device-management.png)

4. 追加のデバイスをオンボードする必要がある場合は、[**オンボーディング**]を選択します。

5. これらの追加デバイスに導入する方法を[**導入方法**]リストから選択し、[**パッケージをダウンロード**]します。

6. 「[Windows 10 マシンのオンボーディングツールと方法](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)」の適切な手順に従います。 このリンクをクリックすると、手順 5 で選択した導入パッケージと一致する Microsoft Defender for Endpoint の手順にアクセスできるランディング ページが表示されます。
    - グループポリシーを使用した Windows 10 マシンのオンボード
    - Microsoft Endpoint Configuration Manager を使用した Windows 10 マシンのオンボード
    - モバイルデバイス管理ツールを使用した Windows 10 マシンのオンボード
    - ローカルスクリプトを使用した Windows 10 マシンのオンボード
    - 非永続的な仮想デスクトップインフラストラクチャ (VDI) マシンをオンボーディングします。

完了後、エンドポイントがオンボードされ、[**デバイス**]テーブルの下に表示され、**Activity エクスプローラー** に監査ログのレポートを開始します。

> [!NOTE]
>これは、ライセンス執行時でのエクスペリエンスです。 必要なライセンスがないと、データは表示されず、アクセスできません。

### <a name="viewing-endpoint-dlp-alerts-in-dlp-alerts-management-dashboard"></a>DLP 警告管理ダッシュボードでのエンドポイント DLP 警告の表示

1. Microsoft 365 コンプライアンス センターの [データ損失防止] ページを開き、[アラート] を選択します。

2. エンドポイント DLP ポリシーの警告を表示するには、「[DLP ポリシーの警告を構成および表示する方法](dlp-configure-view-alerts-policies.md)」の手順を参照してください。

### <a name="viewing-endpoint-dlp-data-in-activity-explorer"></a>Activity エクスプローラーでのEndpoint DLPデータの表示

1. Microsoft 365 コンプライアンスセンターでドメインの[データ分類ページ](https://compliance.microsoft.com/dataclassification?viewid=overview)を開き、Activity エクスプローラーを選択します。

2. エンドポイントデバイスのすべてのデータにアクセスしてフィルタリングするには、「[Activity エクスプローラースタートガイド](data-classification-activity-explorer.md)」の手順に従ってください。

   > [!div class="mx-imgBorder"]
   > ![エンドポイント デバイスのアクティビティ エクスプローラー フィルター。](../media/endpoint-dlp-4-getting-started-activity-explorer.png)

## <a name="next-steps"></a>次の手順

デバイスがオンボードされ、Activity Explorer でアクティビティデータを表示できるようになりました。次の手順に進み、機密アイテムを保護する DLP ポリシーを作成します。

- [エンドポイントのデータ損失防止の使用](endpoint-dlp-using.md)

## <a name="see-also"></a>関連項目

- [エンドポイント データ損失防止について](endpoint-dlp-learn-about.md)
- [エンドポイントのデータ損失防止の使用](endpoint-dlp-using.md)
- [データ損失防止について](dlp-learn-about-dlp.md)
- [DLP ポリシーの作成、テスト、調整](create-test-tune-dlp-policy.md)
- [Activity Explorer を使い始める](data-classification-activity-explorer.md)
- [Microsoft Defender for Endpoint](/windows/security/threat-protection/)
- [Windows 10 マシン用のオンボーディングツールとメソッド](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)
- [Microsoft 365 サブスクリプション](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)
- [Azure AD に参加しているデバイス](/azure/active-directory/devices/concept-azure-ad-join)
- [Chromium ベースの新しい Microsoft Edge をダウンロードする](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)
