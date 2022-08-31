---
title: Microsoft Defender ウイルス対策通知を構成する
description: エンドポイントで標準の Microsoft Defender ウイルス対策通知と他の Microsoft Defender ウイルス対策通知の両方を構成およびカスタマイズする方法について説明します。
keywords: 通知, Defender, ウイルス対策, エンドポイント, 管理, 管理者
ms.service: microsoft-365-security
ms.subservice: mde
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.topic: article
ms.author: deniseb
ms.custom: nextgen
ms.date: 10/18/2021
ms.reviewer: ''
manager: dansimp
ms.collection: M365-security-compliance
ms.openlocfilehash: af6889be3f64d45f7a7237453e2050664de301bf
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2022
ms.locfileid: "67473251"
---
# <a name="configure-microsoft-defender-antivirus-notifications-that-appear-on-endpoints"></a>エンドポイントに表示される Microsoft Defender ウイルス対策通知を構成する

**適用対象:**

- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Microsoft Defender ウイルス対策

**プラットフォーム**
- Windows

Windows 10とWindows 11では、マルウェアの検出と修復に関するアプリケーション通知は、より堅牢で一貫性があり、簡潔です。 Microsoft Defender ウイルス対策の通知は、スキャンが完了し、脅威が検出されるとエンドポイントに表示されます。 通知は、スケジュールされたスキャンと手動でトリガーされたスキャンの両方に従います。 これらの通知は **通知センター** にも表示され、スキャンと脅威の検出の概要が一定の時間間隔で表示されます。

組織のセキュリティ チームの一員である場合は、システムの再起動を求める通知や、脅威が検出されて修復されたことを示す通知など、エンドポイントでの通知の表示方法を構成できます。

## <a name="configure-antivirus-notifications-using-group-policy-or-the-windows-security-app"></a>グループ ポリシーまたはWindows セキュリティ アプリを使用してウイルス対策通知を構成する

Windows セキュリティ [アプリ](microsoft-defender-security-center-antivirus.md)とグループ ポリシーで、最近の脅威検出の概要などの追加通知の表示を構成できます。

> [!NOTE]
> Windows 10バージョン 1607 では、この機能は **拡張通知** と呼ばれ、**Windows 設定** \> **更新プログラム&セキュリティ** \> **Windows Defender** で構成されました。 Windows 10とWindows 11のすべてのバージョンのグループ ポリシー設定では、通知機能は **拡張通知** と呼ばれます。

### <a name="use-group-policy-to-disable-additional-notifications"></a>グループ ポリシーを使用して追加の通知を無効にする

1. グループ ポリシー管理コンピューターで、[グループ ポリシー管理コンソール](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))を開きます。

2. 構成するグループ ポリシー オブジェクトを右クリックし、[編集] を選択 **します**。

3. **グループ ポリシー管理エディター** で、**[コンピューターの構成]** に移動します。

4. [ **管理用テンプレート] を選択します**。

5. ツリーを **Windows コンポーネント** \> **の Microsoft Defender ウイルス対策** > **レポートに展開します**。

6. [ **強化された通知をオフにする**] をダブルクリックし、オプションを **[有効]** に設定します。 次に [**OK**] を選びます。 これにより、追加の通知が表示されなくなります。

> [!IMPORTANT]
> 追加の通知を無効にした場合、脅威の検出や修復アラートなどの重要な通知は無効になりません。

### <a name="use-the-windows-security-app-to-disable-additional-notifications"></a>Windows セキュリティ アプリを使用して追加の通知を無効にする

1. タスク バーのシールド アイコンをクリックするか、スタート メニューで **[セキュリティ**] を検索して、Windows セキュリティ アプリを開きます。

2. **[ウイルス&脅威保護**] タイル (または左側のメニュー バーのシールド アイコン) を選択し、[**ウイルス&脅威対策の設定**] を選択します。

3. **[通知]** セクションまでスクロールし、[**通知設定の変更**] を選択します。

4. スイッチを **[オフ]** または **[オン]** にスライドして、追加の通知を無効または有効にします。

> [!IMPORTANT]
> 追加の通知を無効にした場合、脅威の検出や修復アラートなどの重要な通知は無効になりません。

## <a name="configure-standard-notifications-on-endpoints-using-group-policy"></a>グループ ポリシーを使用してエンドポイントに対する標準通知を構成する

グループ ポリシーを使用すると、次のことができます。

- ユーザーがアクションを実行する必要がある場合に、エンドポイントに追加のカスタマイズされたテキストを表示する
- エンドポイントのすべての通知を非表示にする
- エンドポイントでの再起動通知を非表示にする

通知を非表示にすると、Microsoft Defender ウイルス対策インターフェイス全体を非表示にできない場合に役立ちます。 詳細については、「 [ユーザーが Microsoft Defender ウイルス対策ユーザー インターフェイスを表示または操作できないように](prevent-end-user-interaction-microsoft-defender-antivirus.md) する」を参照してください。 通知の非表示は、ポリシーがデプロイされたエンドポイントでのみ行われます。 実行する必要があるアクション (再起動など) に関連する通知は、[Microsoft エンドポイント マネージャー Endpoint Protection 監視ダッシュボードとレポート](/configmgr/protect/deploy-use/monitor-endpoint-protection)に引き続き表示されます。 

エンドポイント通知にカスタム連絡先情報を追加するには、「[組織のWindows セキュリティ アプリをカスタマイズする」を参照してください](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center)。

### <a name="use-group-policy-to-hide-notifications"></a>グループ ポリシーを使用して通知を非表示にする

1. グループ ポリシー管理コンピューターで、[グループ ポリシー管理コンソール](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))を開きます。

2. 構成するグループ ポリシー オブジェクトを右クリックし、[編集] を選択 **します**。

3. **グループ ポリシー管理エディター** で **[コンピューターの構成**] に移動し、[**管理用テンプレート**] を選択します。

4. ツリーを **Windows コンポーネント** \> **Microsoft Defender ウイルス対策** \> **クライアント インターフェイス** に展開します。 

5. [ **すべての通知を抑制]** をダブルクリックし、オプションを **[有効]** に設定します。 

6. **[OK]** を選択します。 これにより、追加の通知が表示されなくなります。

### <a name="use-group-policy-to-hide-reboot-notifications"></a>グループ ポリシーを使用して再起動通知を非表示にする

1. グループ ポリシー管理コンピューターで、[グループ ポリシー管理コンソール](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))を開きます。

2. 構成するグループ ポリシー オブジェクトを右クリックし、[**編集]** を選択します。

2. **グループ ポリシー管理エディター** で、**[コンピューターの構成]** に移動します。

3. [ **管理用テンプレート]** をクリックします。

4. ツリーを **Windows コンポーネント** \> **Microsoft Defender ウイルス対策** \> **クライアント インターフェイス** に展開します。

5. **[再起動通知を抑制]** をダブルクリックし、オプションを **[有効]** に設定します。 

5. **[OK]** を選択します。 これにより、追加の通知が表示されなくなります。

> [!TIP]
> 他のプラットフォームのウイルス対策関連情報を探している場合は、次を参照してください。
> - [macOS 上で Microsoft Defender for Endpoint 用の基本設定を設定する](mac-preferences.md)
> - [Mac 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
> - [Intune の Microsoft Defender ウイルス対策の macOS ウイルス対策ポリシー設定](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Linux 上で Microsoft Defender for Endpoint 用の基本設定を設定する](linux-preferences.md)
> - [Linux 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-linux.md)
> - [Android 機能用 Defender for Endpoint を構成する](android-configure.md)
> - [iOS 機能用 Microsoft Defender for Endpoint を構成する](ios-configure-features.md)