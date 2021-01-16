---
title: Basic Mobility and Security でのデバイス セキュリティ ポリシーの作成
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: Basic Mobility and Security を使用して、組織情報を保護するデバイス ポリシーを作成します。
ms.openlocfilehash: 077f1e7e0d763aaecfc38fd4b57d9e8912900a3c
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/15/2021
ms.locfileid: "49877070"
---
# <a name="create-device-security-policies-in-basic-mobility-and-security"></a>Basic Mobility and Security でのデバイス セキュリティ ポリシーの作成

Basic Mobility and Security を使用すると、Microsoft 365 の組織情報を不正アクセスから保護するデバイス ポリシーを作成できます。 ポリシーは、デバイスのユーザーが該当する Microsoft 365 ライセンスを持ち、デバイスを Basic Mobility and Security に登録している組織内の任意のモバイル デバイスに適用できます。

## <a name="before-you-begin"></a>はじめに

> [!IMPORTANT]
> モバイル デバイス ポリシーを作成する前に、Basic Mobility and Security をアクティブ化して設定する必要があります。 詳細については、「Basic Mobility and Security の概要」を参照してください。

- Basic Mobility and Security がサポートするデバイス、モバイル デバイス アプリ、セキュリティ設定について説明します。 「Basic [Mobility and Security の機能」を参照してください](capabilities.md)。
- ポリシーを展開する Microsoft 365 ユーザー、および Microsoft 365 へのアクセスがブロックされるのを除外する可能性があるユーザーを含むセキュリティ グループを作成します。 組織に新しいポリシーを展開する前に、少ない数のユーザーに展開してポリシーをテストすることをお勧めします。 自分だけか、ポリシーをテストできる Microsoft 365 の少人数のユーザーを含むセキュリティ グループを作成して使用できます。 セキュリティ グループの詳細については、「セキュリティ グループを作成、 [編集、または削除する」を参照してください](https://go.microsoft.com/fwlink/p/?LinkId=518555)。
- Microsoft 365 で Basic Mobility and Security ポリシーを作成および展開するには、Microsoft 365 のグローバル管理者である必要があります。詳細については、セキュリティ/コンプライアンス [センターの「アクセス許可&参照してください](https://support.microsoft.com/office/d10608af-7934-490a-818e-e68f17d0e9c1)。
- ポリシーを展開する前に、Basic Mobility and Security にデバイスを登録する場合の潜在的な影響を組織に知らせておく必要があります。 ポリシーの設定方法によっては、準拠しないデバイスが Microsoft 365 とデータ (登録済みデバイスにインストールされているアプリケーション、写真、個人情報など) へのアクセスをブロックされ、データを削除できます。

>[!NOTE]
>Microsoft 365 Business Standard の Basic Mobility and Security で作成されたポリシーとアクセス ルールは、Exchange 管理センターで作成された Exchange ActiveSync モバイル デバイス メールボックス ポリシーとデバイス アクセス ルールを上書きします。 デバイスを Microsoft 365 Business Standard の Basic Mobility and Security に登録すると、そのデバイスに適用される Exchange ActiveSync モバイル デバイス メールボックス ポリシーまたはデバイス アクセス ルールは無視されます。 Exchange Online の詳細については、「Exchange ActiveSync」 [をExchange ActiveSync覧ください](https://go.microsoft.com/fwlink/p/?LinkId=524380)。

## <a name="step-1-create-a-device-policy-and-deploy-to-a-test-group"></a>手順 1: デバイス ポリシーを作成し、テスト グループに展開する

開始する前に、Basic Mobility and Security をアクティブ化してセットアップしてください。 手順については、「Basic [Mobility and Security の概要」を参照してください](overview.md)。

1. ブラウザーで、次のコマンドを入力します [https://protection.office.com/devicev2](https://protection.office.com/devicev2) 。

2. [**ポリシーの作成**] を選択します。

   :::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="モビリティとセキュリティの基本ポリシー設定":::

3. [ポリシー **設定] ページ** で、組織内のモバイル デバイスに適用する要件を指定します。

4. **電子メール プロファイルの** 管理が必要 : 有効な場合、Basic Mobility and Security によって管理される電子メール プロファイルを持つデバイスは準拠していないと見なされます。 デバイスが正しくターゲットに設定されていない場合、またはユーザーがデバイスでメール アカウントを手動でセットアップした場合、デバイスに管理されたメール プロファイルを設定することはできません。 [無効] **のままにした** 場合 (既定)、この設定はコンプライアンスまたは非コンプライアンスに対して評価されません。 このオプションを選択した場合にユーザーが準拠する方法については、「既存のメール アカウントが見つかりました」を [参照してください](https://docs.microsoft.com/intune-user-help/existing-company-email-account-found)。

5. [この **ポリシーを今すぐ適用しますか?** ] ページで、このポリシーを適用するグループを選択します。

6. [この **ポリシーの作成] を選択します**。

ポリシーは、モバイル デバイスを使用して Microsoft 365 に次回サインインする場合に、ポリシーが適用される各ユーザーのデバイスにプッシュされます。 ユーザーがモバイル デバイスにポリシーを適用したことがない場合は、ポリシーを展開した後、デバイスに Basic Mobility and Security を登録してアクティブ化する手順を含む通知を受け取ります。 詳細については [、「Basic Mobility and Security を使用してモバイル デバイスを登録する」を参照してください](enroll-your-mobile-device.md)。 Intune サービスによってホストされる Basic Mobility and Security への登録が完了するまでは、電子メール、OneDrive、その他のサービスへのアクセスが制限されます。 Intune ポータル サイト アプリを使用して登録を完了すると、ユーザーはサービスを使用できます。ポリシーはデバイスに適用されます。

## <a name="step-2-verify-that-your-policy-works"></a>手順 2: ポリシーが機能することを確認する

デバイス ポリシーを作成したら、組織に展開する前に、ポリシーが期待した通り動作する必要があります。

1. ブラウザーで、次のコマンドを入力します [https://protection.office.com/devicev2](https://protection.office.com/devicev2) 。
2. [管理対象 **デバイスの一覧を表示する] を選択します**。
3. ポリシーが適用されているユーザー デバイスの状態を確認します。 デバイスの **状態** を管理 **する。**
4. デバイスを選択した後、[工場出荷時の設定に戻す] または [管理]ボタンから会社のデータを削除するをクリックして、デバイスでフル ワイプまたは選択的ワイプを実行することもできます。  手順については、「Microsoft 365 でモバイル デバイスをワイプする」を参照してください。

## <a name="step-3-deploy-a-policy-to-your-organization"></a>手順 3: 組織にポリシーを展開する

デバイス ポリシーを作成し、期待通り動作するデバイス ポリシーを確認したら、組織に展開します。

1. From your browser [https://protection.office.com/devicev2](https://protection.office.com/devicev2) type:
2. 展開するポリシーを選択し、適用するグループの横にある [編集 **] を選択します。**
3. 追加するグループを検索し、[選択] を **クリックします**。
4. [閉 **じる] と [****変更] の設定を選択します。**
5. [閉 **じる] および [** 編集 **ポリシー] を選択します。**

ポリシーは、次回モバイル デバイスから Microsoft 365 にサインインする場合に、ポリシーが適用される各ユーザーのモバイル デバイスにプッシュされます。 ユーザーがモバイル デバイスにポリシーを適用していない場合は、Basic Mobility and Security に登録してライセンス認証するための手順を使ってデバイスに通知を受け取ります。 登録が完了すると、ポリシーがデバイスに適用されます。 詳細については [、「Basic Mobility and Security を使用してモバイル デバイスを登録する」を参照してください](enroll-your-mobile-device.md)。

## <a name="step-4-block-email-access-for-unsupported-devices"></a>手順 4: サポートされていないデバイスの電子メール アクセスをブロックする

組織の情報をセキュリティで保護するには、Basic Mobility and Security でサポートされていないモバイル デバイスの Microsoft 365 メールへのアプリ アクセスをブロックする必要があります。 サポートされているデバイスの一覧については、「サポートされているデバイス [」を参照してください](https://support.microsoft.com/office/capabilities-of-basic-mobility-and-security-a1da44e5-7475-4992-be91-9ccec25905b0#bkmk_supporteddevices)。

**アプリへのアクセスをブロックするには:**

1. ブラウザーで、次のコマンドを入力します [https://protection.office.com/devicev2](https://protection.office.com/devicev2) 。
2. [組織 **全体のデバイス アクセス設定の管理] を選択します**。
3. サポートされていないデバイスをブロックするには、[デバイスが **Microsoft 365 の Basic Mobility and Security** でサポートされていない場合] で [ブロック] を選択し、[保存] を選択 **します**。

   :::image type="content" source="../../media/basic-mobility-security/bms-5-block-access.png" alt-text="モビリティとセキュリティの基本ブロック アクセス オプション":::

## <a name="step-5-choose-security-groups-to-be-excluded-from-conditional-access-checks"></a>手順 5: 条件付きアクセス チェックから除外するセキュリティ グループを選択する

一部のユーザーをモバイル デバイスの条件付きアクセス チェックから除外し、それらのユーザーの 1 つ以上のセキュリティ グループを作成した場合は、ここにセキュリティ グループを追加します。 これらのグループのユーザーには、サポートされているモバイル デバイスに適用されるポリシーはありません。 これは、組織で Basic Mobility and Security を使用しなくなった場合に推奨されるオプションです。

1. ブラウザーで、次のコマンドを入力します [https://protection.office.com/devicev2](https://protection.office.com/devicev2) 。

2. [組織 **全体のデバイス アクセス設定の管理] を選択します**。

   :::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="Basic Mobility and Security によるポリシー オプションの作成":::

3. Microsoft  365 へのアクセスをブロックから除外するユーザーを含むセキュリティ グループを追加するには、[追加] を選択します。 この一覧に追加されたユーザーは、サポートされていないデバイスを使用している場合に Microsoft 365 メールにアクセスできます。

4. [グループの選択] パネルで、使用する **セキュリティ グループを選択** します。

5. 名前を選択し、[保存の追加 **]**  >  **をクリックします**。

6. 組織全体 **のデバイス アクセス設定パネルで、[** 保存] を選択 **します**。

   :::image type="content" source="../../media/basic-mobility-security/bms-8-allow-access.png" alt-text="Basic Mobility and Security のアクセスを許可するオプション":::

## <a name="what-is-the-impact-of-security-policies-on-different-device-types"></a>さまざまなデバイスの種類に対するセキュリティ ポリシーの影響

ユーザー デバイスにポリシーを適用する場合、各デバイスへの影響はデバイスの種類によって多少異なります。 さまざまなデバイスに対するポリシーの影響の例については、次の表を参照してください。

|**セキュリティ ポリシー**|**Android 4 以降**|**Samsung KNOX**|**iOS 6 以降**|**注**|
|:-----|:-----|:-----|:-----|:-----|
|暗号化されたバックアップを要求|いいえ|はい|はい|iOS で暗号化されたバックアップが必要です。|
|クラウド バックアップの禁止|はい|はい|はい|Android での Google バックアップをブロックする (灰色表示)、iOS でのクラウド バックアップ。|
|ドキュメントの同期の禁止|いいえ|いいえ|はい|iOS: クラウド内のドキュメントをブロックします。|
|写真の同期の禁止 |いいえ|いいえ|はい|iOS (ネイティブ): 写真ストリームをブロックします。|
|画面キャプチャの禁止 |いいえ|はい|はい|試行時にブロックされます。|
|ビデオ会議をブロックする |いいえ|いいえ|はい|Skype や他のユーザーではなく、iOS で FaceTime がブロックされている。|
|診断データの送信をブロックする |いいえ|はい|はい|Android での Google クラッシュ レポートの送信をブロックします。|
|アプリ ストアへのアクセスをブロックする |いいえ|はい|はい|Android ホーム ページでアプリ ストア アイコンが見つからない、Windows では無効、iOS では表示されません。|
|アプリ ストアのパスワードを要求する |いいえ|いいえ|はい|iOS: iTunes の購入に必要なパスワード。|
|リムーバブル記憶域への接続をブロックする |いいえ|はい|該当なし|Android: SD カードは設定で灰色表示され、Windows はユーザーに通知します。インストールされたアプリは利用できません|
|Bluetooth 接続の禁止 |メモを参照|メモを参照|はい|Android の設定として BlueTooth を無効にできない。 代わりに、BlueTooth が必要なすべてのトランザクション (高度なオーディオ配布、オーディオ/ビデオ リモート コントロール、ハンズフリー デバイス、ヘッドセット、電話帳アクセス、シリアル ポート) を無効にします。 これらが使用されている場合、ページの下部に小さなトースト メッセージが表示されます。|

## <a name="what-happens-when-you-delete-a-policy-or-remove-a-user-from-the-policy"></a>ポリシーを削除したり、ポリシーからユーザーを削除したりすると、何が起こりますか。

ポリシーを削除するか、ポリシーが展開されたグループからユーザーを削除すると、ポリシー設定、Microsoft 365 メール プロファイル、キャッシュされた電子メールがユーザーのデバイスから削除される可能性があります。 さまざまなデバイスの種類について削除された機能については、次の表をご覧ください。

|**削除された情報**|**iOS 6 以降**|**Android 4 以降 (Samsung KNOX を含む)**|
|:-----|:-----|:-----|
|管理されたメール プロファイル<sup>1</sup>|はい|いいえ|
|クラウド バックアップの禁止|はい|いいえ|

<sup>1</sup>電子メール プロファイルを管理するオプションを選択してポリシーを展開した場合、そのプロファイル内の管理された電子メール プロファイルとキャッシュされた電子メールはユーザー デバイスから削除されます。

ポリシーは、デバイスが Basic Mobility and Security を使用して次回ログインする場合に適用される各ユーザーのモバイル デバイスから削除されます。 これらのユーザー デバイスに適用する新しいポリシーを展開すると、Basic Mobility and Security に再登録するように求めるメッセージが表示されます。

デバイスを完全にワイプするか、デバイスから組織情報を選択的にワイプすることもできます。 詳しくは [、「Basic Mobility and Security」のモバイル デバイスのワイプに関するページをご覧ください](wipe-mobile-device.md)。

## <a name="related-topics"></a>関連項目

[基本的なモビリティとセキュリティの概要](overview.md)

[基本的なモビリティとセキュリティの機能](capabilities.md)
