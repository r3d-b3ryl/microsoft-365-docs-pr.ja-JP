---
title: Android のMicrosoft Defender for Endpointの新機能
description: Android 上の以前のバージョンのMicrosoft Defender for Endpointの主な変更点について説明します。
keywords: microsoft, defender, Microsoft Defender for Endpoint, mac, インストール, macos, whatsnew
ms.prod: m365-security
ms.mktglfcycl: security
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: m365-security-compliance
ms.topic: reference
ms.technology: mde
ms.openlocfilehash: 4300aadd6ab57561592621a0d1aeb54887d70320
ms.sourcegitcommit: f1b3ecde15e5cbbeadaf51b2cadb6b1d677fc265
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2022
ms.locfileid: "67437785"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint-on-android"></a>Android のMicrosoft Defender for Endpointの新機能

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

>[!IMPORTANT]
> Microsoft Defender for Endpointの **マルウェア対策エンジン** が一般公開されました。 この新しいマルウェア保護機能を利用するには、すべてのユーザーに **1.0.3815.0000** を超えるMicrosoft Defender for Endpoint バージョンが必要です。 Microsoft Defender for Endpoint バージョン 1.0.3815.0000 より前のユーザーには、Microsoft Defender for Endpoint アプリケーションを更新するための通知とアプリ内オーバーレイ メッセージが送信されます。 ユーザーはオーバーレイ メッセージに表示されているリンクをクリックして、マネージド プレイ ストアに移動し、アプリケーションを更新できます。 
>
> ユーザーがプレイ ストアにアクセスできない場合は、ポータル サイトからアプリを更新できます。 

## <a name="privacy-controls"></a>プライバシー コントロール

Android のMicrosoft Defender for Endpointでは、管理者とエンド ユーザーの両方のプライバシー コントロールが有効になります。 これには、登録された (MDM) デバイスと登録されていない (MAM) デバイス (プレビュー段階) のコントロールが含まれます。 管理者はアラート レポートでプライバシーを構成できますが、エンド ユーザーは組織に共有される情報を構成できます。 詳細については、「 [プライバシー制御 (MDM)](/microsoft-365/security/defender-endpoint/android-configure#privacy-controls) と [プライバシー制御 (MAM)」](/microsoft-365/security/defender-endpoint/android-configure-mam#configure-privacy-controls)を参照してください。

## <a name="optional-permissions-and-disable-web-protection"></a>オプションのアクセス許可と Web 保護の無効化

Android のMicrosoft Defender for Endpointでは、オンボード フローで **オプションのアクセス許可** が有効になります。 現在、MDE で必要なアクセス許可は、オンボード フローで必須です。 この機能を使用すると、管理者はオンボード中に必須の **VPN** と **アクセシビリティの** アクセス許可を強制することなく、デバイスに MDE を展開できます。 エンド ユーザーは、必須のアクセス許可なしでアプリをオンボードでき、後でこれらのアクセス許可を確認できます。 この機能は現在、登録されていないデバイス (MAM) にのみ存在します。 詳細については、オプションの [アクセス許可](/microsoft-365/security/defender-endpoint/android-configure-mam#optional-permissions)に関するページを参照してください。


## <a name="microsoft-defender-on-android-enterprise-byod-personal-profile"></a>Android エンタープライズ BYOD 個人プロファイルの Microsoft Defender
Microsoft Defender for Endpointは、マルウェア スキャン、フィッシング リンクからの保護、ネットワーク保護、脆弱性管理など、すべての主要な機能を備えた Android Enterprise 個人プロファイル (BYOD のみ) でサポートされるようになりました。 このサポートは、個人プロファイルでユーザーのプライバシーを確保するためのプライバシー [制御](/microsoft-365/security/defender-endpoint/android-configure#privacy-controls) と組み合わせて使用されます。 詳細については、 [お知らせ](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/announcing-the-public-preview-of-defender-for-endpoint-personal/ba-p/3370979) と [デプロイ ガイド](/microsoft-365/security/defender-endpoint/android-intune#set-up-microsoft-defender-in-personal-profile-on-android-enterprise-in-byod-mode)を参照してください。

## <a name="network-protection"></a>ネットワーク保護
Microsoft Defender for Endpointの Network Protection はパブリック プレビュー段階になりました。 ネットワーク保護は、悪意のあるWi-Fi関連する脅威、不正なハードウェア (セキュリティデバイスなど) に対する保護を提供し、関連する脅威が検出された場合にユーザーに通知します。 また、セキュリティで保護されたネットワークに接続し、セキュリティで保護されていない接続に接続するときにネットワークを変更するためのガイド付きエクスペリエンスも表示されます。

これには、Microsoft エンドポイント マネージャー 管理 センター内から機能を構成する機能など、柔軟性を提供するための管理コントロールがいくつか含まれています。 管理者は、プライバシー制御を有効にして、Defender for Endpoint によって Android デバイスから送信されるデータを構成することもできます。 

このパブリック プレビューに参加することに興味がある場合は、networkprotection@microsoft.com でテナント ID を共有してください。 詳細については、「 [ネットワーク保護](/microsoft-365/security/defender-endpoint/android-configure)」を参照してください。

>[!NOTE]
>Microsoft Defender は、1.0.3011.0302 より前のバージョンではサポートされなくなりました。 ユーザーは、デバイスをセキュリティで保護するために、最新バージョンにアップグレードするように要求されます。
更新するには、ユーザーは次の手順を使用できます。
>1. 仕事用プロファイルで、マネージド プレイ ストアに移動します。
>2. 右上隅にあるプロファイル アイコンをタップし、[アプリとデバイスの管理] を選択します。
>3. 利用可能な更新プログラムの下で MDE を見つけて、更新プログラムを選択します。
>
>問題が発生した場合は、 [アプリ内のフィードバックを送信します](/security/defender-endpoint/android-support-signin#send-in-app-feedback)。

## <a name="microsoft-defender-for-endpoint-is-now-microsoft-defender-in-the-play-store"></a>Microsoft Defender for Endpointが Play ストアに Microsoft Defender になりました

Microsoft Defender for Endpointは、Play ストアで **Microsoft Defender** として使用できるようになりました。 この更新プログラムを使用すると、**アプリは米国リージョンのコンシューマー** 向けのプレビューとして利用できるようになります。職場または個人アカウントでアプリにログインする方法に基づいて、Microsoft Defender for Endpointまたは Microsoft Defender for personal の機能にアクセスできます。 詳細については [、このブログ](https://www.microsoft.com/microsoft-365/microsoft-defender-for-individuals) を参照してください。

## <a name="vulnerability-management"></a>脆弱性の管理

2022 年 1 月 25 日に、Android と iOS での脆弱性管理の一般公開が発表されました。 詳細については、 [こちらにある techcommunity の投稿](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/announcing-general-availability-of-vulnerability-management/ba-p/3071663)を参照してください。

## <a name="upcoming-permission-changes-for-microsoft-defender-for-endpoint-running-android-11-or-later-nov-2021"></a>Android 11 以降を実行するMicrosoft Defender for Endpointの今後のアクセス許可の変更 (2021 年 11 月)

リリース ビルド: 1.0.3501.0301 リリース月: 2021 年 11 月 Microsoft Defender for Endpoint、Android API 30 へのアップグレードに [Google](https://developer.android.com/distribute/play-policies#APILevel30) が必要とするこの更新プログラムをリリースしました。 この変更により、Android 11 以降を実行しているデバイスの [新しいストレージアクセス許可](https://developer.android.com/training/data-storage/manage-all-files#all-files-access-google-play)へのアクセスを求めるユーザーが表示されます。 リリース ビルド 1.0.3501.0301 以降で Defender アプリを更新したら、この新しいストレージアクセス許可を受け入れる必要があります。 これにより、Defender for Endpoint のアプリ セキュリティ機能が中断なく機能するようになります。 詳細については、次のセクションを参照してください。

**これは組織にどのような影響を与えますか。** これらの変更は、Android 11 以降を実行しているデバイスでMicrosoft Defender for Endpointを使用し、ビルド 1.0.3501.0301 以降をリリースするために Defender for Endpoint を更新した場合に有効になります。

> [!NOTE]
> 新しいストレージのアクセス許可は、Microsoft エンドポイント マネージャーを介して管理者が "自動承認" するように構成することはできません。 ユーザーは、このアクセス許可へのアクセスを提供するためにアクションを実行する必要があります。

- **ユーザー エクスペリエンス:** ユーザーには、アプリのセキュリティに対するアクセス許可が不足していることを示す通知が表示されます。 ユーザーがこのアクセス許可を拒否した場合、デバイスで "アプリ セキュリティ" 機能がオフになります。 ユーザーがアクセス許可を受け入れるか拒否しない場合、承認されるまで、デバイスのロックを解除するか、アプリを開くときにプロンプトが表示されます。

> [!NOTE]
> 組織が "改ざん保護" 機能をプレビューしていて、最新バージョンに更新してから 7 日以内に新しいストレージのアクセス許可がユーザーによって付与されない場合、ユーザーは企業リソースへのアクセスを失う可能性があります。

**準備に必要な事柄:**

Defender for Endpoint を更新して 1.0.3501.0301 以降のバージョンをビルドした後、ユーザーが新しいアクセス許可を受け入れる必要があることをユーザーとヘルプデスクに通知します (該当する場合)。 アクセス許可を受け入れるには、ユーザーは次の手順を実行する必要があります。

1. Defender for Endpoint のアプリ内通知をタップするか、Defender for Endpoint アプリを開きます。 ユーザーには、必要なアクセス許可を一覧表示する画面が表示されます。 ストレージのアクセス許可の横に緑色のチェック マークが表示されなくなります。

2. [ **開始]** をタップします。

3. **[アクセスを許可してすべてのファイルを管理する]** のトグルをタップします。

4. これで、デバイスが保護されます。

  > [!NOTE]
  > このアクセス許可により、Microsoft Defender for Endpointはユーザーのデバイス上のストレージにアクセスできます。これにより、悪意のあるアプリや不要なアプリの検出と削除に役立ちます。 Microsoft Defender for Endpointアクセス/スキャン Android アプリ パッケージ ファイル (.apk) のみ。 仕事用プロファイルを持つデバイスでは、Defender for Endpoint は作業関連のファイルのみをスキャンします。
