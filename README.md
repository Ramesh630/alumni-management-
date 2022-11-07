
ALTER TABLE survey_maxcount
 ADD FOREIGN KEY (survey_ownerID) REFERENCES user_account(user_ID);

ALTER TABLE survey_forms
 ADD FOREIGN KEY (form_ownerID) REFERENCES user_account(user_ID);

ALTER TABLE survey_question1
 ADD FOREIGN KEY (survey_formID) REFERENCES survey_forms(form_id);
ALTER TABLE survey_question2
 ADD FOREIGN KEY (survey_formID) REFERENCES survey_forms(form_id);
 ALTER TABLE survey_question3
 ADD FOREIGN KEY (survey_formID) REFERENCES survey_forms(form_id);
 ALTER TABLE survey_question4
 ADD FOREIGN KEY (survey_formID) REFERENCES survey_forms(form_id);
 ALTER TABLE survey_question5
 ADD FOREIGN KEY (survey_formID) REFERENCES survey_forms(form_id);
 ALTER TABLE survey_question6
 ADD FOREIGN KEY (survey_formID) REFERENCES survey_forms(form_id);
 ALTER TABLE survey_question7
 ADD FOREIGN KEY (survey_formID) REFERENCES survey_forms(form_id);
 ALTER TABLE survey_question8
 ADD FOREIGN KEY (survey_formID) REFERENCES survey_forms(form_id);


ALTER TABLE user_teacher_detail
 ADD FOREIGN KEY (teacher_civilStat) REFERENCES marital_status(ID);
ALTER TABLE user_student_detail
 ADD FOREIGN KEY (student_civilStat) REFERENCES marital_status(ID);
ALTER TABLE user_admin_detail
 ADD FOREIGN KEY (admin_civilStat) REFERENCES marital_status(ID);



ALTER TABLE message_thread_participant
 ADD FOREIGN KEY (participant_threadID) REFERENCES message_thread(thread_ID);
ALTER TABLE message_thread_participant
 ADD FOREIGN KEY (participant_userID) REFERENCES user_account(user_ID);


ALTER TABLE message_send_state
 ADD FOREIGN KEY (state_msgID) REFERENCES message_send(message_ID);
ALTER TABLE message_send_state
 ADD FOREIGN KEY (state_readerID) REFERENCES user_account(user_ID);

ALTER TABLE forum_comment
 ADD FOREIGN KEY (comment_topicID) REFERENCES forum_topic(topic_ID);
ALTER TABLE forum_comment
 ADD FOREIGN KEY (comment_userID) REFERENCES user_account(user_ID);


ALTER TABLE forum_comment_reply
 ADD FOREIGN KEY (comment_reply_parentID) REFERENCES forum_comment(comment_ID);

ALTER TABLE forum_comment_reply
 ADD FOREIGN KEY (comment_reply_userID) REFERENCES user_account(user_ID);

ALTER TABLE user_notification
 ADD FOREIGN KEY (notif_topicID) REFERENCES forum_comment(comment_ID);
ALTER TABLE user_notification
 ADD FOREIGN KEY (notif_userID) REFERENCES user_account(user_ID);
ALTER TABLE user_notification
 ADD FOREIGN KEY (notif_receiverID) REFERENCES user_account(user_ID);
