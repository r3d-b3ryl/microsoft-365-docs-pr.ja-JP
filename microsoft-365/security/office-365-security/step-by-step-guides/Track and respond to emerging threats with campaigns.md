---
title: Microsoft Defender for Office 365で表示されるキャンペーンを使用して、新たに発生するセキュリティの脅威を追跡し、対応する
description: Microsoft Defender for Office 365内の脅威キャンペーンのチュートリアルを参照して、組織に対する協調的な電子メール攻撃を調査する方法を示します。
search.product: ''
search.appverid: ''
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: m365-guidance-templates
ms.topic: how-to
ms.technology: mdo
ms.openlocfilehash: 32571de4b4eaf5302d14842cda727ddc7850a6d1
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2022
ms.locfileid: "67483567"
---
# <a name="track-and-respond-to-emerging-threats-with-campaigns-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365のキャンペーンを使用して、新たな脅威を追跡し、対応する

キャンペーンは、組織に対する協調的な電子メール攻撃を調査できるため、新たな脅威の追跡と対応に使用できます。 新しい脅威が組織を対象とするため、Microsoft Defender for Office 365は悪意のあるメッセージを自動的に検出して関連付けます。 

## <a name="what-you-will-need"></a>必要なもの
- Microsoft Defender for Office 365プラン 2 (E5 プランに含まれます)。
- 十分なアクセス許可 (セキュリティ 閲覧者ロール)。
- これらの手順を実行するには、5 分から 10 分です。

## <a name="what-is-a-campaign-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365のキャンペーンとは

キャンペーンとは、1 つまたは複数の組織に対する組織的なメール攻撃のことです。 資格情報と会社のデータを盗むEmail攻撃は、大規模で有益な業界です。 攻撃を阻止するテクノロジが拡大し、乗算されるにつれて、攻撃者は成功を続けるためにメソッドを変更します。

Microsoft は、サービス全体で膨大な量のフィッシング対策、スパム対策、マルウェア対策データを活用して、キャンペーンの特定に役立ちます。 次のようないくつかの要因に従って、攻撃情報を分析して分類します。

- **攻撃元**: 送信元 IP アドレスと送信者の電子メール ドメイン。
- **メッセージのプロパティ: メッセージ** の内容、スタイル、トーン。
- **メッセージ受信者**: 受信者の関連付け (受信者ドメイン、受信者の仕事機能 (管理者やエグゼクティブなど)、会社の種類 (大規模、小規模、パブリック、プライベートなど)、業界など。
- **攻撃ペイロード**: メッセージ内の悪意のあるリンク、添付ファイル、またはその他のペイロード。

キャンペーンは有効期間が短い場合もあれば、アクティブ期間と非アクティブ期間の数日間、数週間、または数か月にわたる場合もあります。 特定の組織に対してキャンペーンが開始される場合もあれば、組織が *複数* の会社にまたがる大規模なキャンペーンの一部である場合もあります。

> [!TIP]
> キャンペーン内で使用可能なデータの詳細については、[Microsoft Defender for Office 365のキャンペーン ビューを](/microsoft-365/security/office-365-security/campaigns)参照してください。

## <a name="watch-the-exploring-campaign-views-video"></a>キャンペーンビューの *探索ビデオを見* る

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWGBL8]

## <a name="investigating-a-suspicious-email-campaign-using-threat-reports"></a>脅威レポートを使用した疑わしいメール キャンペーンの調査

キャンペーンが組織をターゲットにしており、その影響の詳細を確認したい場合は、次の手順を実行します。 
1. [キャンペーン ページ](https://security.microsoft.com/campaigns)に移動します。
1. 調査するキャンペーン名を選択します。 
1. ポップアップが開いたとき、[ **脅威レポートのダウンロード**] を選択します。
1. 脅威レポートを開くと、キャンペーンに関する詳細情報が表示されます。 レポートの情報には、次のものが含まれます。 
- **エグゼクティブサマリー：** キャンペーンの種類と、組織内でターゲットとするユーザーの数の概要。 
- **分析：** キャンペーンの開始時のタイムライン グラフ、組織を対象とするメッセージの数、メッセージの宛先と判定。 
- **攻撃の起点:** 組織内の受信トレイに配信されたメッセージの数が多い上位の送信 IP アドレスとドメイン。 これにより、組織をターゲットにしているユーザーを調査できます。 
- **Email テンプレートとペイロード:** キャンペーンの一部であったメールの件名行と、キャンペーンの一部として存在する URL (およびその頻度)。
- **推奨 事項：** メッセージを修復するための次の手順に関する推奨事項。

## <a name="investigate-inboxed-messages-that-are-part-of-a-email-threat-campaign"></a>電子メール脅威キャンペーンの一部である受信トレイメッセージを調査する

1. [キャンペーン ページ](https://security.microsoft.com/campaigns)に移動します。
1. グラフの下にある **[詳細] ビュー** で、キャンペーンの一覧をスクロールします。
1. 調査するキャンペーン名を選択します。 キャンペーンのクリック数が 0 を超える場合は、組織内のユーザーが URL をクリックしたか、メールからファイルをダウンロードしたことを示します。
1. キャンペーン ポップアップにはキャンペーンに関する詳細情報が表示され、グラフにはキャンペーンの開始日から終了日までのキャンペーンのタイムラインが表示され、水平方向のフロー図には、キャンペーンの配信元、判定、メッセージの現在の場所からのステージが表示されます。
1. フロー図の下にある [ **URL クリック** ] タブを選択して、クリックに関する情報を表示します。 ここでは、URL をクリックしたユーザー、ユーザーが優先度アカウント ユーザーとしてタグ付けされている場合、URL 自体、およびクリックした時刻を確認できます。 
1. 受信トレイとクリックされたメッセージの詳細を確認する場合は、[**受信トレイ** メッセージの **探索** > ] を選択します。 新しいタブが開き、脅威エクスプローラーに移動します。 
1. エクスプローラーの **詳細ビュー** では **、最新の配信** を参照して、メッセージがまだ受信トレイに残っているか、システム ZAP によって検疫に移動されたかを判断できます。 _特定のメッセージの詳細を取得するには、メッセージを選択します。ポップアップは追加情報を提供します。ポップアップの左上にある **[電子メール エンティティを開く] ページ** を選択すると、新しいタブが開き、メッセージに関する詳細情報が表示されます。_
1.  アクションを実行して受信トレイからメッセージを移動する場合は、メッセージを選択し、[**メッセージ アクション** を **迷惑フォルダーに移動**]  >  を選択できます。 これにより、ユーザーは、侵害の可能性のある悪意のあるメッセージとやり取りし続けなくなります。 

## <a name="next-steps"></a>次の手順

詳細については、[Microsoft Defender for Office 365のキャンペーン ビューを参照](/microsoft-365/security/office-365-security/campaigns)してください。
