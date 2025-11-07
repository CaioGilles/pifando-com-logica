CC = gcc
CFLAGS = -Wall -Wextra -std=c99 -Iinclude

SRC_DIR = src
BUILD_DIR = build
TARGET = $(BUILD_DIR)/game

SOURCES = $(wildcard $(SRC_DIR)/*.c)
OBJECTS = $(patsubst $(SRC_DIR)/%.c,$(BUILD_DIR)/%.o,$(SOURCES))

$(TARGET): $(OBJECTS) | $(BUILD_DIR)
  $(CC) $(CFLAGS) $(OBJECTS) -o $@

$(BUILD_DIR):
  mkdir -p $(BUILD_DIR)

$(BUILD_DIR)/%.o: $(SRC_DIR)/%.c | $(BUILD_DIR)
  $(CC) $(CFLAGS) -c $< -o $@

.PHONY: all clean

all: $(TARGET)

clean:
  rm -rf $(BUILD_DIR)
