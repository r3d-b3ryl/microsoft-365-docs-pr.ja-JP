---
title: Microsoft Defender for Businessでセットアップ ウィザードを使用する
description: Defender for Business を使用すると、Defender for Business を初めて使用するときに実行されるウィザードを使用して簡単にセットアップできます。 セットアップ ウィザードの動作を確認します。
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: article
ms.prod: m365-security
ms.technology: mdb
ms.localizationpriority: medium
ms.date: 08/09/2022
ms.reviewer: shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
- m365-initiative-defender-business
ms.custom: intro-get-started
ms.openlocfilehash: e1bf29eb817649f2e736da2a80aed3b0108157a5
ms.sourcegitcommit: 9b10e56b9e83f3a80757fa6108bebd1d80cf4178
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/12/2022
ms.locfileid: "67319957"
---
# <a name="use-the-setup-wizard-in-microsoft-defender-for-business"></a>Microsoft Defender for Businessでセットアップ ウィザードを使用する

Defender for Business は、中小企業の時間と労力を節約できるよう設計されています。 たとえば、セットアップ ウィザードを使用して初期セットアップと構成を行うことができます。 セットアップ ウィザードでは、セキュリティ チームへのアクセス許可の付与、セキュリティ チームの電子メール通知の設定、会社の Windows デバイスのオンボードについて説明します。

> [!TIP]
> セットアップ ウィザードの使用は省略可能です。 セットアップと構成プロセスを手動で実行することもできます。 詳細については、次を参照してください。
> - [ウィザードを使用しない場合はどうなりますか?](#what-happens-if-i-dont-use-the-wizard)
> - [Defender for Business を設定して構成する方法](mdb-setup-configuration.md)

## <a name="how-to-start-the-setup-wizard"></a>セットアップ ウィザードを開始する方法

セットアップ ウィザードは、会社のユーザーが Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) に初めてサインインした場合に実行するように設計されています。 

会社がMicrosoft 365 Business Premiumを使用している場合、誰かが **Endpoints** > **デバイス インベントリ** に初めてアクセスすると、Defender for Business セットアップ ウィザードが実行されます。 

セットアップ ウィザードの開始画面は、次の図のようになります。

:::image type="content" source="media/mdb-wizard-start.png" alt-text="Defender for Business を設定するためのウィザードのホーム画面のスクリーンショット。":::

## <a name="the-setup-wizard-flow"></a>セットアップ ウィザードフロー

> [!IMPORTANT]
> セットアップ ウィザードを実行するには、グローバル管理者である必要があります。 Microsoft 365 または Defender for Business に会社をサインアップしたユーザーは、既定でグローバル管理者です。

セットアップ ウィザードは、Defender for Business のセットアップと構成を迅速かつ効率的に行えるように設計されています。 ウィザードでは、次の手順を実行します。

1. **ユーザーにアクセス許可を割り当てる**。 この手順では、セキュリティ チームにMicrosoft 365 Defender ポータル ()[https://security.microsoft.com](https://security.microsoft.com) へのアクセス権を付与します。 このポータルでは、お客様とセキュリティ チームがセキュリティ機能を管理し、アラートを表示し、検出された脅威に対して必要なアクションを実行します。 ポータルへのアクセスは、特定のアクセス許可を意味するロールを通じて付与されます。

   Defender for Business では、セキュリティ チームのメンバーに次の 3 つのロールのいずれかを割り当てることができます。<br/>
   
   - **グローバル 管理**: グローバル管理者は、Microsoft 365 テナント全体のすべての設定を表示および編集できます。 グローバル管理者は、会社の Microsoft 365 サブスクリプションの初期セットアップと構成を行います。 
   - **セキュリティ管理者**: セキュリティ管理者は、セキュリティ設定を表示および編集し、脅威が検出されたときにアクションを実行できます。
   - **セキュリティ リーダー**: セキュリティ リーダーはレポート内の情報を表示できますが、セキュリティ設定を変更することはできません。 

   [役割とアクセス許可に関する詳細を学ぶ](mdb-roles-permissions.md)。 

2. **電子メール通知を設定します**。 この手順では、セキュリティ チームの電子メール通知を設定できます。 その後、アラートが生成されたとき、または新しい脆弱性が検出された場合、セキュリティ チームは、自分のデスクから離れていても、それを見逃すことはありません。 [電子メール通知の詳細については、こちらを参照してください](mdb-email-notifications.md)。 

3. **Windows デバイスをオンボードして構成する**。 この手順では、会社の Windows デバイスを Defender for Business にすばやくオンボードできます。 デバイスをすぐにオンボードすると、初日からデバイスを保護できます。 [Defender for Business へのデバイスのオンボードの詳細について説明します](mdb-onboard-devices.md)。

   - **Intuneを使用していない場合は**、Microsoft 365 Defender ポータルでデバイスをオンボードできます。 
   - **Microsoft Intuneを既に使用していて**、会社にデバイスがIntuneに登録されている場合は、Intuneを引き続き使用できます。 [Microsoft Intuneでのエンドポイント セキュリティの管理に関するページを参照](/mem/intune/protect/endpoint-security)してください。
   
4. **セキュリティ ポリシーを構成します**。 Defender for Business には、会社のデバイスに適用し、次世代の保護とファイアウォール保護を実現する既定のセキュリティ ポリシーが搭載されています。 これらの既定のポリシーでは、推奨される設定が使用され、デバイスに強力な保護を提供するように設計されています。 独自のセキュリティ ポリシーを作成することもできます。 [セキュリティ ポリシーと設定の表示と編集に関する説明を参照してください](mdb-configure-security-settings.md)。

   > [!NOTE]
   > 既にIntuneを使用してデバイスとセキュリティ ポリシーを管理している場合は、Microsoft エンドポイント マネージャー管理センターを引き続き使用できます。 [Microsoft Intuneでのエンドポイント セキュリティの管理に関するページを参照](/mem/intune/protect/endpoint-security)してください。


## <a name="what-is-automatic-onboarding"></a>自動オンボードとは何ですか?

自動オンボードは、Windows デバイスを Defender for Business にオンボードするための簡単な方法です。 自動オンボードは、Microsoft Intuneに既に登録されている Windows デバイスでのみ使用できます。 

セットアップ ウィザードを使用しているときに、Windows デバイスが既にIntuneに登録されているかどうかをシステムが検出します。 検出されたデバイスのすべて、または一部に対して自動オンボードを使用するかどうかを確認するメッセージが表示されます。 すべての Windows デバイスを一度にオンボードすることも、最初に特定のデバイスを選択してから、後でデバイスを追加することもできます。 

他のデバイスをオンボードするには、「 [Defender for Business にデバイスをオンボードする」を](mdb-onboard-devices.md)参照してください。

> [!TIP]
> - [すべてのデバイスを登録] オプションを選択することをお勧めします。 そうすれば、後で Windowsデバイスが Intune に登録されると、自動的に Defender for Business にオンボードされます。 
> - エンドポイント マネージャー管理センターでセキュリティ ポリシーと設定を管理している場合は、Microsoft 365 Defender ポータルに切り替えて、デバイス、ポリシー、および設定を管理することをお勧めします。 詳細については、「 [セキュリティ ポリシーとデバイスを管理する場所の選択](mdb-configure-security-settings.md#choose-where-to-manage-security-policies-and-devices)」を参照してください。

## <a name="what-happens-if-i-dont-use-the-wizard"></a>ウィザードを使用しない場合はどうなりますか?

セットアップ ウィザードの使用は省略可能です。 ウィザードを使用しないことを選択した場合、またはセットアップ プロセスが完了する前にウィザードが閉じられる場合は、自分でセットアップと構成プロセスを完了できます。 

次の手順を実行するには、「 [Defender for Business のセットアップと構成」](mdb-setup-configuration.md) を参照してください。

1. セキュリティ チームが Microsoft 365 Defender ポータル ()[https://security.microsoft.com](https://security.microsoft.com) にアクセスして使用できるように **[、ロールとアクセス許可を割り当てます](mdb-roles-permissions.md)**。

2. 新しいアラートや脆弱性に関するループに入るように **[、セキュリティ チームの電子メール通知を設定](mdb-email-notifications.md)** します。

3. **[Defender](mdb-onboard-devices.md)** for Business によって保護されるようにデバイスをオンボードします。

4. 次世代の保護、ファイアウォール保護、Web コンテンツ のフィルター処理など、**[セキュリティ ポリシーを管理](mdb-configure-security-settings.md)** します。

## <a name="next-steps"></a>次の手順

- [より多くのデバイスを Defender for Business にオンボードする](mdb-onboard-devices.md)
- [Defender for Business でセキュリティ ポリシーと設定を表示および編集する](mdb-configure-security-settings.md)