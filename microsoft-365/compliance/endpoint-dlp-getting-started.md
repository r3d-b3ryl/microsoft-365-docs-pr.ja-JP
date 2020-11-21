---
title: Microsoft 365 エンドポイント データ損失防止を開始する
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/21/2020
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: Microsoft 365 エンドポイントのデータ損失防止を設定して、ファイルアクティビティを監視し、それらのファイルの保護アクションをエンドポイントに実装します。
ms.openlocfilehash: 8211ffbe3a84c0ee9fb4cb4c22d4dcea7f906a78
ms.sourcegitcommit: bdf65d48b20f0f428162c39ee997accfa84f4e5d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/20/2020
ms.locfileid: "49371603"
---
# <a name="get-started-with-endpoint-data-loss-prevention"></a>エンドポイント データ損失防止を開始する

Microsoft Endpoint Data Loss Prevention (Endpoint DLP) は、Microsoft 365 サービス全体で機密アイテムを検出して保護する Microsoft 365 Data Loss Prevention (DLP) スイートの機能の一部です。 Microsoft のすべての DLP 製品 の詳細については、 「[データ損失防止の概要](data-loss-prevention-policies.md)」を参照してください。 エンドポイント DLP の詳細については、「[エンドポイント データ損失防止の説明](endpoint-dlp-learn-about.md)」を参照してください。

Microsoft エンドポイント DLP を使用すると、Windows 10 デバイスを監視し、機密アイテムが使用され、共有されていることを検出できます。これにより、それらが適切に使用され、保護されていることを確認し、それらを危険にさらす可能性のある危険な動作を防ぐために必要な可視性と制御が得られます。

## <a name="before-you-begin"></a>開始する前に

### <a name="skusubscriptions-licensing"></a>SKU /サブスクリプション ライセンス

エンドポイント DLP の使用を開始する前に、 [Microsoft 365 サブスクリプション](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)とアドオンを確認する必要があります。エンドポイント DLP 機能にアクセスして使用するには、次のいずれかのサブスクリプションまたはアドオンが必要です。

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

エンドポイント DLP からのデータは、[アクティビティ エクスプローラー](data-classification-activity-explorer.md)で表示できます。アクティビティ エクスプローラーへのアクセス許可を付与する役割は 4 つあります。データへのアクセスに使用するアカウントは、次のいずれかのメンバーでなければなりません。

- グローバル管理者
- コンプライアンス管理者
- セキュリティ管理者
- コンプライアンスデータ管理者

### <a name="prepare-your-endpoints"></a>エンドポイントを準備する

これらの要件を満たすために、Endpoint DLP の導入を計画している Windows 10 デバイスを確認してください。

1. Windows 10 x64 ビルド 1809 以降を実行している必要があります。

2. マルウェア対策クライアントのバージョンは、4.18.2009.7 以降です。Windows セキュリティ アプリを開いて現在のバージョンを確認し、[設定] アイコンを選び、[バージョン情報] を選択します。バージョン番号はマルウェア対策クライアント バージョンの下に表示されます。Windows Update KB4052623 をインストールして、最新のマルウェア対策クライアント バージョンに更新します。注: Windows セキュリティ コンポーネントをアクティブにする必要はありません。エンドポイント DLP は、Windows セキュリティの状態に関係なく実行できます。

3. 次の Windows Update がインストールされています。注: これらの更新プログラムは、デバイスをエンドポイント DLP にオンボードするための前提条件ではありませんが、重要な問題の修正が含まれているため、製品を使用する前にインストールする必要があります。

    - Windows 10 1809 の場合 - KB4559003、KB4577069、KB4580390
    - Windows 10 1903 または 1909 の場合 - KB4559004、KB4577062、KB4580386
    - Windows 10 2004 の場合 - KB4568831、KB4577063
    - Office 2016 を実行しているデバイスの場合 (他の Office バージョンではない) - KB4577063 

4. すべてのデバイスは [Azure Active Directory (Azure AD) に参加する ](https://docs.microsoft.com/azure/active-directory/devices/concept-azure-ad-join)か、Hybrid Azure AD に参加する必要があります。

5. エンドポイント デバイスに Microsoft Chromium Edge ブラウザーをインストールして、クラウドへのアップロード アクティビティのポリシー アクションを適用します。詳しくは、「[Chromium ベースの新しい Microsoft Edge をダウンロードする](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)」を参照してください。

6. Microsoft 365 Apps バージョン 2004 - 2008 の月次エンタープライズ チャネルを使用している場合、Office コンテンツを分類するエンドポイント DLP に既知の問題があり、バージョン 2009 以降に更新する必要があります。現在のバージョンについては「[Microsoft 365 アプリの更新履歴 (日付別の一覧)](https://docs.microsoft.com/officeupdates/update-history-microsoft365-apps-by-date)」をご覧ください。この問題の詳細については、[2020 年の最新のチャネル リリースのリリース ノート](https://docs.microsoft.com/officeupdates/current-channel#version-2010-october-27)の「Office スイート」セクションを参照してください。

## <a name="onboarding-devices-into-device-management"></a>デバイス管理へのデバイスのオンボーディング

デバイス上の機密アイテムを監視および保護する前に、デバイスの監視を有効にし、エンドポイントをオンボードする必要があります。これらのアクションはどちらも Microsoft 365 コンプライアンス ポータルで行われます。

まだオンボードされていないデバイスをオンボードする場合は、適切なスクリプトをダウンロードして、それらのデバイスに展開します。「[デバイスのオンボーディング](endpoint-dlp-getting-started.md#onboarding-devices)」の手順に従ってください。

既に [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/) にオンボードされているデバイスがある場合、それらは管理対象デバイスのリストに表示されます。「[Microsoft Defender for Endpoint にオンボードされているデバイスを使用する](https://docs.microsoft.com/microsoft-365/compliance/endpoint-dlp-getting-started?view=o365-worldwide&source=docs#with-devices-onboarded-into-microsoft-defender-for-endpoint)」の手順に従ってください。

### <a name="onboarding-devices"></a>デバイスのオンボーディング

この導入シナリオでは、まだオンボーディングされていないデバイスをオンボードし、Windows 10 デバイスで意図しない共有から機密アイテムを監視および保護します。

1. [Microsoft コンプライアンスセンター](https://compliance.microsoft.com)を開きます。

2. コンプライアンスセンターの設定ページを開き、[**オンボードデバイス**]を選択します。 

   > [!div class="mx-imgBorder"]
   > ![デバイス管理を有効にする](../media/endpoint-dlp-learn-about-1-enable-device-management.png)

   > [!NOTE]
   > 通常は、デバイスのオンボーディングが有効になるまでに約 60 秒かかりますが、Microsoft サポートを利用する前に最大 30 分お待ちください。

3. **[デバイス管理]** を選択して、**[デバイス]** リストを開きます。

4. オンボーディング プロセスを開始するには、**[オンボーディング]** を選択します。

5. これらの追加デバイスに導入する方法を[**導入方法**]リストから選択し、**パッケージをダウンロード** します。

   > [!div class="mx-imgBorder"]
   > ![展開方法](../media/endpoint-dlp-getting-started-3-deployment-method.png)
   
6. 「[Windows 10 マシンのオンボーディング ツールと方法](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)」の適切な手順に従います。このリンクをクリックすると、手順 5 で選択した展開パッケージと一致する Microsoft Defender for Endpoint の手順にアクセスできるランディング ページが表示されます。

    - グループポリシーを使用したWindows 10 マシンのオンボード
    - Microsoft Endpoint Configuration Manager を使用した Windows 10 マシンのオンボード
    - モバイルデバイス管理ツールを使用した Windows 10 マシンのオンボード
    - ローカルスクリプトを使用した Windows 10 マシンのオンボード
    - 非永続的な仮想デスクトップインフラストラクチャ (VDI) マシンをオンボーディングします。

完了後、エンドポイントがオンボードされ、デバイス リストに表示されます。アクティビティ エクスプローラーへの監査アクティビティ ログのレポートも開始されます。

> [!NOTE]
> これは、ライセンス執行時でのエクスペリエンスです。 必要なライセンスがないと、データは表示されず、アクセスできません。

### <a name="with-devices-onboarded-into-microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpoint にオンボードされているデバイスを使用する

このシナリオでは、既に Microsoft Defender for Endpoint が展開されていて、レポートしているエンドポイントがあります。これらのすべてのエンドポイントが管理対象デバイスのリストに表示されます。「[デバイスのオンボーディング](endpoint-dlp-getting-started.md#onboarding-devices)」の手順を使用して、引き続き新しいデバイスをエンドポイント DLP にオンボードしてカバレッジを拡大することができます。

1. [Microsoft コンプライアンス センター](https://compliance.microsoft.com)を開きます。

2. コンプライアンス センターの設定ページを開き、**[デバイスの監視を有効にする]** を選択します。

3. **[デバイス管理]** を選択して、**[デバイス]** リストを開きます。既に Microsoft Defender for Endpoint にレポートしているデバイスのリストが表示されます。

   > [!div class="mx-imgBorder"]
   > ![デバイス管理](../media/endpoint-dlp-getting-started-2-device-management.png)
   
4. 追加のデバイスをオンボードする必要がある場合は、[**オンボーディング**]を選択します。

5. これらの追加デバイスに展開する方法を **[展開方法]** リストから選択し、**パッケージをダウンロード** します。

6. 「[Windows 10 マシンのオンボーディング ツールと方法](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)」の適切な手順に従います。このリンクをクリックすると、手順 5 で選択した展開パッケージと一致する Microsoft Defender for Endpoint の手順にアクセスできるランディング ページが表示されます。

    - グループポリシーを使用したWindows 10 マシンのオンボード
    - Microsoft Endpoint Configuration Manager を使用した Windows 10 マシンのオンボード
    - モバイルデバイス管理ツールを使用した Windows 10 マシンのオンボード
    - ローカルスクリプトを使用した Windows 10 マシンのオンボード
    - 非永続的な仮想デスクトップインフラストラクチャ (VDI) マシンをオンボーディングします。

完了後、エンドポイントがオンボードされ、**[デバイス]** テーブルに表示され、**アクティビティ エクスプローラー** に監査ログのレポートを開始します。

> [!NOTE]
>これは、ライセンス執行時でのエクスペリエンスです。 必要なライセンスがないと、データは表示されず、アクセスできません。

### <a name="viewing-endpoint-dlp-alerts-in-dlp-alerts-management-dashboard"></a>DLP アラート管理ダッシュボードでのエンドポイント DLP アラートの表示

1. Microsoft 365 コンプライアンス センターの [データ損失防止] ページを開き、[アラート] を選択します。

2. エンドポイント DLP ポリシーの警告を表示するには、「[DLP ポリシーの警告を構成および表示する方法](dlp-configure-view-alerts-policies.md)」の手順を参照してください。


### <a name="viewing-endpoint-dlp-data-in-activity-explorer"></a>アクティビティ エクスプローラーでのエンドポイント DLP データの表示

1. Microsoft 365 コンプライアンスセンターでドメインの[データ分類ページ](https://compliance.microsoft.com/dataclassification?viewid=overview)を開き、Activity エクスプローラーを選択します。

2. エンドポイントデバイスのすべてのデータにアクセスしてフィルタリングするには、「[Activity エクスプローラースタートガイド](data-classification-activity-explorer.md)」の手順に従ってください。

   > [!div class="mx-imgBorder"]
   > ![エンドポイント デバイスのアクティビティ エクスプローラー フィルター](../media/endpoint-dlp-4-getting-started-activity-explorer.png)

## <a name="next-steps"></a>次の手順
デバイスがオンボードされ、Activity Explorer でアクティビティデータを表示できるようになりました。次の手順に進み、機密アイテムを保護する DLP ポリシーを作成します。

- [エンドポイントのデータ損失防止の使用 (プレビュー) ](endpoint-dlp-using.md)

## <a name="see-also"></a>こちらもご覧ください

- [エンドポイントのデータ損失防止について学ぶ (プレビュー) ](endpoint-dlp-learn-about.md)
- [エンドポイントのデータ損失防止の使用 (プレビュー) ](endpoint-dlp-using.md)
- [データ損失防止の概要](data-loss-prevention-policies.md)
- [DLP ポリシーの作成、テスト、調整](create-test-tune-dlp-policy.md)
- [Activity Explorer を使い始める](data-classification-activity-explorer.md)
- [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/)
- [Windows 10 マシン用のオンボーディングツールとメソッド](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)
- [Microsoft 365 サブスクリプション](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)
- [Azure AD に参加しているデバイス](https://docs.microsoft.com/azure/active-directory/devices/concept-azure-ad-join)
- [Chromium ベースの新しい Microsoft Edge をダウンロードする](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)
